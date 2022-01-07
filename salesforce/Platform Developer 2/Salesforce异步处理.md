

## 异步处理

### 概述

| Type           | Overview                                                 | Common Scenarios    |
| :------------- | :------------------------------------------------------- | :------------------ |
| Future Methods | 另外启动线程 在程序空闲是执行 （执行顺序无法保障）       | Web service callout |
| Batch Apex     | 处理超出制限的大量数据                                   | 数据清理或记录归档  |
| Queueable Apex | 类似@future,但可按指定顺序执行，且可用相对复杂的数据类型 | 按顺序访问外部 Web  |
| Scheduled Apex | 在指定时间执行                                           | 每日或每周任务      |

异步的优点：

- 更高限制
- 异步限制与最初将异步请求排队的同步请求中的限制无关
- 处理能力提升
- 异步处理的优先级低于通过浏览器和 API 进行的实时交互，会根据内存和 CPU 使用率等系统资源情况，减少异步执行

[制限文档](https://developer.salesforce.com/docs/atlas.en-us.224.0.apexcode.meta/apexcode/apex_gov_limits.htm)

### @future

####   应用场景

- Callouts to external Web services
- 做一些时间上不是特别着急动作
- 处理一会费时间的操作
- 有些SObject不能在DML操作中一起使用，用future来做另外的可以解决  * [不能在 DML 操作中一起使用的对象](https://developer.salesforce.com/docs/atlas.en-us.224.0.apexcode.meta/apexcode/apex_dml_non_mix_sobjects.htm)

####   注意点：

- ```java
  global class SomeClass {
    // 1.Future 方法必须是静态方法，
    // 2.只能返回 void 类型。
    // 3.指定的参数必须是原始数据类型、原始数据类型数组或原始数据类型的集合。
    // 4.不能将标准或自定义对象作为参数
    // 5.常见的模式是向方法传List<Id>
    @future
    public static void someFutureMethod(List<Id> recordIds) {
      List<Account> accounts = [Select Id, Name from Account Where Id IN :recordIds];
      // process account records to do awesome stuff
    }
  }
  ```

- future无法保证顺序，更新相同的记录时，可能会锁定记录或出现其他不好现象
- 调用外部服务或 API 时，@future(callout=true)
- 每个future方法的调用都会向异步队列添加一个请求，因此请避免在短时间内添加大量未来请求
  - 确保未来的方法尽可能快地执行
  - 如果调用外部服务时，尽量callout的方法统一到一起。
  - 测试时候 数据集合尽量在200条，测试是否会出现延迟。
  - Batch Apex更合适的时候，要用Batch Apex

####   测试：

- ```java
  public class SMSUtils {
      // Call async from triggers, etc, where callouts are not permitted.
      @future(callout=true)
      public static void sendSMSAsync(String fromNbr, String toNbr, String m) {
          String results = sendSMS(fromNbr, toNbr, m);
          System.debug(results);
      }
      // Call from controllers, etc, for immediate processing
      public static String sendSMS(String fromNbr, String toNbr, String m) {
          // Calling 'send' will result in a callout
          String results = SmsMessage.send(fromNbr, toNbr, m);
          insert new SMS_Log__c(to__c=toNbr, from__c=fromNbr, msg__c=results);
          return results;
      }
  }
  ```

  
  
  ```java
  // mock数据需要implements HttpCalloutMock接口
  @isTest
  global class SMSCalloutMock implements HttpCalloutMock {
      global HttpResponse respond(HttpRequest req) {
          // Create a fake response
          HttpResponse res = new HttpResponse();
          res.setHeader('Content-Type', 'application/json');
          res.setBody('{"status":"success"}');
          res.setStatusCode(200);
          return res;
      }
  }
  ```
  
  
  
  ```java
  // 测试代码包含在 startTest 和 stopTest 测试方法之间,这些异步进程将同步运行
  @IsTest
  private class Test_SMSUtils {
    @IsTest
    private static void testSendSms() {
      Test.setMock(HttpCalloutMock.class, new SMSCalloutMock());
      Test.startTest();
        SMSUtils.sendSMSAsync('111', '222', 'Greetings!');
      Test.stopTest();
      // runs callout and check results
      List<SMS_Log__c> logs = [select msg__c from SMS_Log__c];
      System.assertEquals(1, logs.size());
      System.assertEquals('success', logs[0].msg__c);
    }
  }
  ```

####   要记住的事情

- 带有future注解的方法必须是静态方法，只能返回void类型。
- 指定的参数必须是原始数据类型、原始数据类型数组或原始数据类型集合；Future的方法不能将对象作为参数。
- 未来的方法不一定按照调用它们的顺序执行。此外，两个未来的方法可能会同时运行，如果这两个方法更新相同的记录，这可能会导致记录锁定。
- 不能在 Visualforce 控制器中的 getMethodName()、setMethodName() 或构造函数中使用 Future 方法。
- 您不能从Future方法调用Future方法。您也不能在运行 future 方法时调用调用 future 方法的触发器。请参阅参考资料中的链接，以防止将来出现递归方法调用。
- getContent() 和 getContentAsPDF() 方法不能用在带有 future 注释的方法中。
- 每次 Apex 调用仅限于 50 次未来调用，并且对 24 小时内的调用次数有额外限制。有关限制的更多信息，请参阅下面的链接。
- Futureメソッドをバッチメソッドから呼び出すことはできません。



### Batch Apex

####   特点：

- 新的制限

- 如果一个批处理未能成功处理，则所有其他成功的批处理事务都不会回滚

- Callouts时，指定Database.AllowsCallouts

  - ```
    public class SearchAndReplace implements Database.Batchable<sObject>, 
       Database.AllowsCallouts{
    }
    ```

- 必须实现Database.Batchable 接口

  - start()

    - 用于收集记录或对象给execute用
    - Batch Apex 作业开始时调用一次，并返回 Database.QueryLocator 对象或包含传递给作业的记录或对象的 Iterable
    - 使用 QueryLocator 对象，可以绕过 SOQL 查询检索的记录总数的调控器限制,最多可以查询 5000 万条记
    - 对于 Iterable，SOQL 查询检索的记录总数的调控器限制仍然有效。

  - execute()

    - 一次默认执行200条
    - 并行顺序无法保证
    - 对 Database.BatchableContext 对象的引用。或List<sObject>

  - finish()

    - 于执行后处理操作（例如，发送电子邮件），并在所有批次处理完毕后调用一次

    ```java
    public class MyBatchClass implements Database.Batchable<sObject> {
        public (Database.QueryLocator | Iterable<sObject>) start(Database.BatchableContext bc) {
            // collect the batches of records or objects to be passed to execute
        }
        public void execute(Database.BatchableContext bc, List<P> records){
            // process each batch of records
        }
        public void finish(Database.BatchableContext bc){
            // execute any post-processing operations
        }
    }
    ```

####   调用批处理类

- ```java
  // 要调用批处理类，只需将其实例化，然后使用实例调用 Database.executeBatch：
  MyBatchClass myBatchObject = new MyBatchClass();
  Id batchId = Database.executeBatch(myBatchObject);
  
  // 可以选择传递第二个范围参数来指定应该传递给每个批处理的 execute 方法的记录数。专业提示：如果您遇到调控器限制，您可能希望限制此批处理大小。
  Id batchId = Database.executeBatch(myBatchObject, 100);
  
  // 每个批处理 Apex 调用都会创建一个 AsyncApexJob 记录，以便您可以跟踪作业的进度。您可以通过 SOQL 查看进度或在 Apex 作业队列中管理您的作业。我们将很快讨论作业队列。
  AsyncApexJob job = [SELECT Id, Status, JobItemsProcessed, TotalJobItems, NumberOfErrors FROM AsyncApexJob WHERE ID = :batchId ];
  ```

  

```java
public class UpdateContactAddresses implements
    Database.Batchable<sObject>, Database.Stateful {
    // instance member to retain state across transactions
    public Integer recordsProcessed = 0;
    public Database.QueryLocator start(Database.BatchableContext bc) {
        return Database.getQueryLocator(
            'SELECT ID, BillingStreet, BillingCity, BillingState, ' +
            'BillingPostalCode, (SELECT ID, MailingStreet, MailingCity, ' +
            'MailingState, MailingPostalCode FROM Contacts) FROM Account ' +
            'Where BillingCountry = \'USA\''
        );
    }
    public void execute(Database.BatchableContext bc, List<Account> scope){
        // process each batch of records
        List<Contact> contacts = new List<Contact>();
        for (Account account : scope) {
            for (Contact contact : account.contacts) {
                contact.MailingStreet = account.BillingStreet;
                contact.MailingCity = account.BillingCity;
                contact.MailingState = account.BillingState;
                contact.MailingPostalCode = account.BillingPostalCode;
                // add contact to list to be updated
                contacts.add(contact);
                // increment the instance member counter
                recordsProcessed = recordsProcessed + 1;
            }
        }
        update contacts;
    }
    public void finish(Database.BatchableContext bc){
        System.debug(recordsProcessed + ' records processed. Shazam!');
        AsyncApexJob job = [SELECT Id, Status, NumberOfErrors,
            JobItemsProcessed,
            TotalJobItems, CreatedBy.Email
            FROM AsyncApexJob
            WHERE Id = :bc.getJobId()];
        // call some utility to send email
        EmailUtils.sendMessage(job, recordsProcessed);
    }
}
```



```java
// 测试
@isTest static void test() {
        Test.startTest();
        UpdateContactAddresses uca = new UpdateContactAddresses();
        Id batchId = Database.executeBatch(uca);
        Test.stopTest();
        // after the testing stops, assert records were updated properly
        System.assertEquals(10, [select count() from contact where MailingCity = 'New York']);
    }
```



### Queueable Apex

#### 特点

- 用了@future的简单性和Batch Apex 的强大功能，并将它们混合在一起形成了 Queueable Apex

- 非原始类型：您的 Queueable 类可以包含非原始数据类型的成员变量，例如 sObjects 或自定义 Apex 类型。可以在作业执行时访问这些对象。
- 调用 System.enqueueJob 监控： System.enqueueJob的返回值为AsyncApexJobId
- 链接作业：可以通过从正在运行的作业启动第二个作业

#### 要记住的事情

- 根据[异步 Apex 方法执行](https://developer.salesforce.com/docs/atlas.en-us.224.0.apexcode.meta/apexcode/apex_gov_limits.htm#asyncExecutionLimit)的[共享限制，](https://developer.salesforce.com/docs/atlas.en-us.224.0.apexcode.meta/apexcode/apex_gov_limits.htm#asyncExecutionLimit)排队作业的执行计数一次。
- 您可以在单个事务中使用 System.enqueueJob 将多达 50 个作业添加到队列中。
- 链接作业时，您只能使用 System.enqueueJob 从正在执行的作业中添加一个作业，这意味着每个可排队的父作业只能存在一个子作业。从同一个可排队作业启动多个子作业是一个禁忌。
- 对链接作业的深度没有限制，这意味着您可以将一个作业链接到另一个作业，并对每个新的子作业重复此过程以将其链接到新的子作业。但是，对于 Developer Edition 和 Trial 组织，链接作业的最大堆栈深度为 5，这意味着您可以将作业链接四次，并且链中的最大作业数为 5，包括初始父级可排队作业

```java
public class UpdateParentAccount implements Queueable {
    private List<Account> accounts;
    private ID parent;
    public UpdateParentAccount(List<Account> records, ID id) {
        this.accounts = records;
        this.parent = id;
    }
    public void execute(QueueableContext context) {
        for (Account account : accounts) {
          account.parentId = parent;
          // perform other processing or callout
        }
        update accounts;
    }
}
```

```java
// find all accounts in ‘NY’
List<Account> accounts = [select id from account where billingstate = ‘NY’];
// find a specific parent account for all records
Id parentId = [select id from account where name = 'ACME Corp'][0].Id;
// instantiate a new instance of the Queueable class
UpdateParentAccount updateJob = new UpdateParentAccount(accounts, parentId);
// enqueue the job for processing
ID jobID = System.enqueueJob(updateJob);
```

```java
@isTest
public class UpdateParentAccountTest {
    @testSetup
    static void setup() {
        List<Account> accounts = new List<Account>();
        // add a parent account
        accounts.add(new Account(name='Parent'));
        // add 100 child accounts
        for (Integer i = 0; i < 100; i++) {
            accounts.add(new Account(
                name='Test Account'+i
            ));
        }
        insert accounts;
    }
    static testmethod void testQueueable() {
        // query for test data to pass to queueable class
        Id parentId = [select id from account where name = 'Parent'][0].Id;
        List<Account> accounts = [select id, name from account where name like 'Test Account%'];
        // Create our Queueable instance
        UpdateParentAccount updater = new UpdateParentAccount(accounts, parentId);
        // startTest/stopTest block to force async processes to run
        Test.startTest();
        System.enqueueJob(updater);
        Test.stopTest();
        // Validate the job ran. Check if record have correct parentId now
        System.assertEquals(100, [select count() from account where parentId = :parentId]);
    }
}
```

```java
public class FirstJob implements Queueable {
    public void execute(QueueableContext context) {
        // Awesome processing logic here
        // Chain this job to next job by submitting the next job
        System.enqueueJob(new SecondJob());
    }
}
```



### Apex Scheduler

```java
global class RemindOpptyOwners implements Schedulable {
    global void execute(SchedulableContext ctx) {
        List<Opportunity> opptys = [SELECT Id, Name, OwnerId, CloseDate
            FROM Opportunity
            WHERE IsClosed = False AND
            CloseDate < TODAY];
        // Create a task for each opportunity in the list
        TaskUtils.remindOwners(opptys);
    }
}

RemindOpptyOwners reminder = new RemindOpptyOwners();
// Seconds Minutes Hours Day_of_month Month Day_of_week optional_year
String sch = '20 30 8 10 2 ?';
String jobID = System.schedule('Remind Opp Owners', sch, reminder);
```

#### 要记住的事情

- 您一次只能有 100 个计划的 Apex 作业，并且每 24 小时内有最大计划的 Apex 执行次数。有关详细信息，请参阅参考资料部分中的执行调控器和限制。
- 如果您计划从触发器安排课程，请格外小心。您必须能够保证触发器不会添加超过限制的计划作业。
- 计划的 Apex 不支持同步 Web 服务调出。为了能够进行标注，通过将标注放置在用@future(callout=true) 注释的方法中并从预定的 Apex 调用此方法来进行异步标注。但是，如果您计划的 Apex 执行批处理作业，则批处理类支持标注。

### Monitor Asynchronous Apex

- Setup -> Apex ジョブ
- AsyncApexJob jobInfo = [SELECT Status, NumberOfErrors    FROM AsyncApexJob WHERE Id = :jobID];

- Apex Flex 最多100个。
- 按先进先出的顺序处理
- 可以查看当前的队列顺序并重新排列队列
- 每个组织，批处理系统最多可以同时处理五个排队或活动的作业
- Monitoring Scheduled Jobs的话 CronTrigger ct = [SELECT TimesTriggered, NextFireTime FROM CronTrigger WHERE Id = :jobID];
- 

