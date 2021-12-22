#### Salesforce Developer I 知识点

---

#### Sandbox

| 種別          | Matadate Copy | Data Cope | 更新間隔 | データストレージ制限        |
| ------------- | ------------- | --------- | -------- | --------------------------- |
| Developer     | YES           | NO        | 1 日     | 200MB                       |
| Developer Pro | YES           | NO        | 1 日     | 1GB                         |
| Partial Copy  | YES           | 一部      | 5 日     | 5GB                         |
| Full          | YES           | YES       | 29 日    | 本番環境と同様 (コピー時点) |

---

#### 保存数据顺序

[参考资料](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_triggers_order_of_execution.htm)

1. System Validation Rules
2. Apex Before Triggers
3. Custom Validation Rules
4. Duplicate Rules
5. Apex After Triggers
6. Assignment Rules
7. Auto-Response Rules
8. Workflow Rules
9. Processes
10. Escalation Rules
11. Roll-Up Summary Fields
12. Commits all DML operations to the database.
13. sending email and executing enqueued asynchronous Apex jobs 

---

#### 制限

Per-Transaction Apex Limits

| 点   | 描述                                                         | 同步        | 异步                                             |
| ---- | ------------------------------------------------------------ | ----------- | ------------------------------------------------ |
| A    | 发出的 SOQL 查询总数                                         | 100         | 200                                              |
| A    | SOQL 查询检索到的记录总数                                    |             | 50000                                            |
| C    | 检索到的记录总数 Database.getQueryLocator                    |             | 10000                                            |
| A    | 发出的 SOSL 查询总数                                         |             | 20                                               |
| A    | 单个 SOSL 查询检索到的记录总数                               |             | 2000                                             |
| A    | 发出的 DML 语句总数                                          |             | 150                                              |
| A    | 由于 DML 语句而处理的记录总数，审批流程， 要么 database.emptyRecycleBin |             | 10000                                            |
|      | 由于以下原因递归触发触发器的任何 Apex 调用的总堆栈深度 插入, 更新， 要么 删除 报表3 |             | 16                                               |
| B    | 事务中的调用总数（HTTP 请求或 Web 服务调用）                 |             | 100                                              |
|      | 事务中所有调出（HTTP 请求或 Web 服务调用）的最大累积超时     |             | 120 秒                                           |
|      | 最大方法数 未来 每个 Apex 调用允许注释                       | 50          | 0 在批处理和未来的上下文中；1 在可排队的上下文中 |
|      | 添加到队列的最大 Apex 作业数 System.enqueueJob               | 50          | 1                                                |
|      | 总人数 发电子邮件 允许的方法                                 |             | 10                                               |
|      | 总堆大小4                                                    | 6 MB        | 12MB                                             |
|      | Salesforce 服务器上的最大 CPU 时间5                          | 10,000 毫秒 | 60,000 毫秒                                      |
| B    | 每个 Apex 交易的最长执行时间                                 |             | 10分钟                                           |
|      | 每个 Apex 事务允许的最大推送通知方法调用数                   |             | 10                                               |
|      | 每个推送通知方法调用中可以发送的最大推送通知数               |             | 2000                                             |
|      | 最大数量 EventBus.publish 调用配置为立即发布的平台事件       |             | 150                                              |

Static Apex Limits

|      | 描述                                                  | 限制                                      |
| ---- | ----------------------------------------------------- | ----------------------------------------- |
| C    | 事务中标注（HTTP 请求或 Web 服务调用）的默认超时      | 10 秒                                     |
| C    | 标注请求或响应（HTTP 请求或 Web 服务调用）的最大大小1 | 6 MB 用于同步 Apex 或 12 MB 用于异步 Apex |
|      | Salesforce 取消事务前的最长 SOQL 查询运行时间         | 120 秒                                    |
|      | Apex 部署中的最大类和触发器代码单元数                 | 7500                                      |
|      | Apex 触发器批量大小                                   | 200                                       |
| B    | For 循环列表批量大小                                  | 200                                       |
| B    | 为 Batch Apex 查询返回的最大记录数 数据库.查询定位器  | 5000万                                    |

---

#### 数据权限

1. **組織レベル**
 - 承認されたユーザの管理

 - パスワードポリシーの設定

 - プロファイルごとに特定の時間と場所（IPアドレス）にログインを制限

   

2. Objectレベル

 - プロファイルごとにオブジェクトへのアクセス権限の設定

 - CRUD設定

   

3. 项目级别
 - プロファイルごとに項目へのアクセス権限の設定

  - 参照、編集

    

4. レコーダーレベル
 - 組織の共有設定
 - ロール階層
 - 共有ルール
 - ルールの直接設定 

5. Apex共有ルール

[引用](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_classes_keywords_sharing.htm)

 - with sharing, without sharing, inherited shared
 - 表記なしの場合、クロスの呼び出し元によって適用が異なる

   1. 匿名ブロックの場合、共有ルールが適用される
   2. トリガーの場合、共有ルールが適用されない
   3. 別クラスの場合、呼び出し元クラスが「with sharing」の場合のみ共有ルールが適用される

    -   Both inner and outer class can be declared as with sharing
    - Inner class donot inherit the sharing setting from the container class
    -   inherited sharing のある Apex クラスは、次の用途に使用する場合、with sharing として実行されます。
        - Aura コンポーネントコントローラ
        - Visualforce コントローラ
        - Apex REST サービス
        - その他の Apex トランザクションへの開始ポイント

---

#### 测试

- 75%のコードカバレージ率が必要

- @isTest (static testMethod ~ methodname(){}は、現在非推奨)

- @testSetup

- @isTest(seeAlldata = true)を使用すると、そのクラスやメソッドは組織のすべてのレコードにアクセス可能

- テストクラスがPrivate テストメソッドがstatic

- Test.startTest() と　Test.stopTest()

- ユーザごとにのwith sharingをテストするために、System.runAs(testUser)

- IDはハードコートしないこと

- TestVisible

- getStandardPricebookId() => Returns the ID of the standard price book in the organization.

- The @testSetup annotation cannot be used when the @isTest(SeeAllData=True) annotation is used

- **运行测试：**
  
  - The Apex Test Execution page in Salesforce Setup.
  - The Test menu in the Developer Console.
  
- 测试数据哪里来

  - 写个类专门用于生成数据（工厂类）
  - 从静态文件csv中导入
  - [@isTest](https://github.com/isTest)(SeeAllData=True) 注意此时不可用@testSetup

   

---

#### Debug

**debug leave**

- NONE
- ERROR
- WARN
- INFO
- DEBUG
- FINE
- FINER
- FINEST

but user don’t see debug statements in levels “Info” or lower.

debug log filter settings

- The Show More link on the debug log’s record.
- The Log Filters tab on a class or trigger detail page.

For which three items can a trace flag be configured

- Automated Process
- Platform Integration
- User
- Apex Class
- Apex Trigger

---

#### 层级

<img src="http://4.bp.blogspot.com/-jd45jUE538s/Tw8h9Q3iwWI/AAAAAAAAAX4/0Cs7Fsazz2Q/s1600/Componets.jpg" alt="层级图"  />

**Declarative Components**

- User Interface
  - Applications,
  - Page Layouts
  - Tabs
  - Record Types
- Business Logic
  - WorkFlow
  - Validation Rules
  - Assignment Rules
  - Approval Processes
- Data Model
  - Object
  - Fields
  - Relationship

**Programming Components**

- User Interface
  - Visaulforce Pages
  - Web Controlers
  - Force.com Sites
- Business Logic
  - VF Controller
  - Apex
  - Web Service Api
- Data Model
  - Web Service API
  - Metadata API

问题

**What is the difference between Declarative Interface and Programmatic Interface?**

- Declarative Interface - Setup Menu; Point & Click.
- Programmatic Interface - Coding; Extends basic functionality.

---

#### roll-up summary

[文档](https://help.salesforce.com/s/articleView?id=sf.fields_about_roll_up_summary_fields.htm&type=5)

- COUNT
- SUM
- MIN
- MAX



特点有很多

- Any custom object that is on the master side of a master-detail relationship

- Any standard object that is on the master side of a master-detail relationship with a custom object

- Opportunities using the values of opportunity products related to the opportunity

  - Quote ⇒ Opportunity 
  - OpportunityLineItem ⇒ Opportunity 

- Accounts using the values of related opportunities

  - Opportunity  ⇒ Account

- Campaigns using campaign member status or the values of campaign member custom fields

  - CampaignMember   ⇒ Campaign

- 如果您的组织使用多种货币，则主记录的货币决定汇总汇总字段的货币。例如，如果主记录和明细记录的币种不同，则明细记录值转换为主记录的币种。

- 避免从子记录中引用汇总汇总字段。从子记录引用的汇总汇总字段可能具有过时的值，因为它们的父记录尚未更新。相反，从父记录引用汇总汇总字段。您的汇总汇总字段将始终具有更新的值，因为该规则在父值更新后运行。

  如果您尝试在父汇总汇总字段上强制执行 25 条记录限制，请在您的子对象上创建验证规则。添加子记录时，子对象上的验证规则可以检查计数是否已经为 25 或更多。

  ```
  AND(ISNEW(), Sample.Line_Count__c >= 25)
  ```

---

允许Administrator以其他身份login

Setup => Login Access Policies => Administrators Can Log in as Any User =>true

---

#### workflow  VS process builder

启动条件

| **workflow**                                                 | **Process builder**                  |
| ------------------------------------------------------------ | ------------------------------------ |
| created                                                      | a  record changes                    |
| created, and every time it's edit                            | A platform event message is received |
| created, and any time it's edited to subsequently meet criteria | It’s invoked by another process      |

Actions

| **workflow**     | **Process builder**      |
| ---------------- | ------------------------ |
| Task             | Apex                     |
| Email Alert      | Create a Record          |
| Field Update     | Email Alerts             |
| Outbound Message | Flows                    |
|                  | Post to Chatter          |
|                  | Processes                |
|                  | Quick Actions            |
|                  | Quip                     |
|                  | Send Custom Notification |
|                  | Submit for Approval      |
|                  | Update Records           |

---

#### Lightning ltng:require

[官方文档](https://developer.salesforce.com/docs/atlas.ja-jp.212.0.lightning.meta/lightning/aura_compref_ltng_require.htm)

```html
<aura:component>
    <ltng:require 
        styles="{!$Resource.SLDSv1 + '/assets/styles/lightning-design-system-ltng.css'}"
        scripts="{!join(',', 
    				$Resource.jsLibraries + '/jsLibOne.js', 
    				$Resource.jsLibraries + '/jsLibTwo.js')}"
        afterScriptsLoaded="{!c.scriptsLoaded}" />
</aura:component>
```

特点：

- 同时加载多个脚本和样式表 from $Resource or controller.js
- 按它们列出的顺序加载
- 如果样式在同一组件或不同组件中的多个 <ltng:require> 标签中指定，则它们仅加载一次。

属性:

| **Attribute Name** | **Attribute Type** | **Description**                                              |
| ------------------ | ------------------ | ------------------------------------------------------------ |
| body               | Component[]        | The body of the component. In markup, this is everything in the body of the tag. |
| scripts            | String[]           | The set of scripts in dependency order that will be loaded.  |
| styles             | String[]           | The set of style sheets in dependency order that will be loaded. |

事件

| **Event Name**         | **Event Type** | **Description**                                              |
| ---------------------- | -------------- | ------------------------------------------------------------ |
| afterScriptsLoaded     | COMPONENT      | Fired when ltng:require has loaded all scripts listed in ltng:require.scripts |
| beforeLoadingResources | COMPONENT      | Fired before ltng:require starts loading resources           |

---

#### Lightning Component framework

benefits：

- It provides an event-driven architecture for better decoupling between components.
- It promotes faster development using out-of-box components that are suitable for desktop and mobile devices.
- It uses a traditional publish-subscribe model.
- t uses an MVC architectural design pattern.

Component Bundles

- Component or Application
- CSS Styles
- Controller
- Design
- Documentation
- Renderer
- Helper
- SVG File

---

### AppExchange Managed and Unmanaged Packages

| Attribute     | Managed Packages                                             | Unmanaged Packages                                           |
| ------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Customization | You can’t view or change the solution’s code or metadata.    | You can customize code and metadata, if desired.             |
| Upgrades      | The provider can automatically upgrade the solution.         | To receive an upgrade, you must uninstall the package from your org and then reinstall a new version from AppExchange. |
| Org limits    | The contents of the package don’t count against the app, tab, and object limits in your org | The contents of the package count against the app, tab, and object limits in your org. |

---

### Exception

```java
// 特点
// 必须 name ends with the word Exception =>MyException
// 必须 extends Exception
public class MyException extends Exception {}


try { 
    // Error
} catch (My1Exception e) { 
   // 下面的实例化方式都可行 
		throw new MyException();
		throw new MyException(‘This is bad’);
		throw new MyException(e);
		throw new MyException(‘This is bad’, e);
} finally {
  System.debug('i am finally');
}
```

---

### Checkpoints

Select Debug | My Current Checkpoints Only to only display checkpoints

- Namespace
- Class
- Line
- Time

Checkpoint Locations

- File
- Line
- Iteration

---

#### Visualforce Page

**Standard Controller**

- 每个 Salesforce 标准对象都存在一个标准控制器。标准控制器是为您预先编写的强大类。
- 可增删改查。
- 遵守共享规则
- Methods
  - addFields(fieldNames)
  - cancel()
  - delete()
  - edit()
  - getId()
  - getRecord()
  - reset()
  - save()
  - view()

```html
<apex:page standardController="Account">
  <apex:form>
    <apex:pageBlock title="My Content" mode="edit">
      <apex:pageBlockButtons>
        <apex:commandButton action="{!save}" value="Save"/>
      </apex:pageBlockButtons>
      <apex:pageBlockSection title="My Content Section" columns="2">
        <apex:inputField value="{!account.name}"/>
        <apex:inputField value="{!account.site}"/>
        <apex:inputField value="{!account.type}"/>
        <apex:inputField value="{!account.accountNumber}"/>
      </apex:pageBlockSection>
    </apex:pageBlock>
  </apex:form>
</apex:page>
```

**Custom Controller**

- 自定义控制器是一个 Apex 类，逻辑随心添加
- 可跨对象增删改查
- 不写with sharing的时候，不遵守sharing rule

```java
public class MyController {
    private final Account account;
    public MyController() {
        account = [SELECT Id, Name, Site FROM Account 
                   WHERE Id = :ApexPages.currentPage().getParameters().get('id')];
    }
    public Account getAccount() {
        return account;
    }
    public PageReference save() {
        update account;
        return null;
    }
}
```

```html
<apex:page controller="myController" tabStyle="Account">
    <apex:form>
        <apex:pageBlock title="Congratulations {!$User.FirstName}">
            You belong to Account Name: <apex:inputField value="{!account.name}"/>
            <apex:commandButton action="{!save}" value="save"/>
        </apex:pageBlock>
    </apex:form>
</apex:page>
```

**Extension Controller**

- 想重写某些标准机能
- extensions可以有多个，如存在相同名字的属性或者方法的话，后者覆盖前者
- 遵守共享规则

```java
public class myControllerExtension {
    private final Account acct;
    // The extension constructor initializes the private member
    // variable acct by using the getRecord method from the standard
    // controller.
    public myControllerExtension(ApexPages.StandardController stdController) {
        this.acct = (Account)stdController.getRecord();
    }
    public String getGreeting() {
        return 'Hello ' + acct.name + ' (' + acct.id + ')';
    }
}
```

```html
<apex:page standardController="Account" extensions="myControllerExtension">
    {!greeting} <p/>
    <apex:form>
        <apex:inputField value="{!account.name}"/> <p/>
        <apex:commandButton value="Save" action="{!save}"/>
    </apex:form>
</apex:page>
```

#### StandardSetController

- 配合这个<apex:pageBlockTable> 做出来的画面可现实分页
- 执行批量更新的记录
- 同Standard Controller页面的一样```<apex:page standardController="Contact" recordSetVar="contacts">```

```java
public class opportunityList2Con {
    // ApexPages.StandardSetController must be instantiated
    // for standard list controllers
    public ApexPages.StandardSetController setCon {
        get {
            if(setCon == null) {
                setCon = new ApexPages.StandardSetController(Database.getQueryLocator(
                    [SELECT Name, CloseDate FROM Opportunity]));
            }
            return setCon;
        }
        set;
    }

    // Initialize setCon and return a list of records
    public List<Opportunity> getOpportunities() {
        return (List<Opportunity>) setCon.getRecords();
    }
}
```

```html
<apex:page controller="opportunityList2Con">
    <apex:pageBlock>
        <apex:pageBlockTable value="{!opportunities}" var="o">
            <apex:column value="{!o.Name}"/>
            <apex:column value="{!o.CloseDate}"/>
        </apex:pageBlockTable>
    </apex:pageBlock>
</apex:page>
```



#### apex:page

[各个属性介绍](https://developer.salesforce.com/docs/atlas.en-us.pages.meta/pages/pages_compref_page.htm)

| **属性名称**       | **属性类型**     | **描述**                                                     |
| ------------------ | ---------------- | ------------------------------------------------------------ |
| action             | ApexPages.Action | 例如， action="{!doAction}" 引用控制器中的 doAction() 方法。<br />如果未指定操作，页面将照常加载。如果 action 方法返回 null，则页面只会刷新。<br />在呈现页面之前调用此方法，并允许您有选择地将用户重定向到另一个页面。<br />**重要提示：**此操作**不**应用于初始化或 DML。 |
| renderAs           | String           | 目前 PDF 是唯一受支持的内容转换器。将此属性设置为“pdf”会将页面呈现为 PDF。 |
| standardController | String           |                                                              |
| extensions         | String           |                                                              |
| controller         | String           |                                                              |
| language           | String           |                                                              |
| recordSetVar       | String           | 该属性指示页面使用面向集合的标准控制器<br /><apex:pageBlockTable value= "{!accounts}" var= "a" > <apex:column value= "{!a.name}" /> </apex:pageBlockTable > |

#### 测试Vusialpage

获取参数

ApexPages.currentPage().getParameters()；=>Map

设置参数

ApexPages.currentPage().getParameters().put(‘input’, ‘TestValue’)

设置当前页

Test.setCurrentPage(pageRef),

---

#### Enum

- 枚举是一种抽象数据类

- 尽管每个值对应于一个不同的整数值，但枚举隐藏了此实现，以便您不会无意中误用这些值，例如使用它们执行算术运算。
- 创建枚举后，可以声明该类型的变量、方法参数和返回类型。

```java
public enum Season {WINTER, SPRING, SUMMER, FALL}

Season e1 = Season.WINTER; 
System.debug(e1); // WINTER

Season e2 = Season.valueOf('SPRING'); 
System.debug(e2); // SPRING

List<Season> eList = Season.values(); 
System.debug(eList); // (WINTER, SPRING, SUMMER, FALL)

// Season变得像类型一样
Season m(Integer x, Season e) {
    // xxx
    return Season.SUMMER;
}
```

---

#### SOQL Injection Defenses

```java
// 避免使用动态 SOQL 查询。相反，使用静态查询和绑定变量。
String queryName = '%' + name + '%';
queryResult = [SELECT Id FROM Contact WHERE (IsDeleted = false and Name like :queryName)];

String qryName = '%' + name + '%’; 
String qryString = 'SELECT Id FROM Contact WHERE Name LIKE :qryNAme';
List queryResults = Database.query(qryString);

// 需要动态SOQL时，需要用String.escapeSingleQuotes(str)处理传入值，此方法将转义字符 (\) 添加到从用户传入的字符串中的所有单引号中。该方法确保所有单引号都被视为封闭字符串
String qryName = '%'+String.escapeSingleQuotes(name)+'%' ; 
List<Contact> queryResults = Database.query('SELECT Id FROM Contact WHERE Name LIKE :qryNAme');
```

---

#### formula fields

- Generate a link using the HYPERLINK function to a specific record.
- Determine if a datetime field value has passed using the NOW function.
- Determine which of three different images to display using the IF function.

---

#### Primitive Data Types

| 数据类型 | 描述                                                         |
  | :------- | :----------------------------------------------------------- |
  | Boolean  | 一个只能赋值 true, false, or null. 例如：`Boolean isWinner = true;` |
  | Date     | Date 值中添加或减去一个 Integer 值，返回一个 Date 值<br />Date myDate = Date.newInstance(1960, 2, 17); <br />Date newDate = mydate.addDays(2);<br />[详细参照](https://developer.salesforce.com/docs/atlas.en-us.234.0.apexref.meta/apexref/apex_methods_system_date.htm) |
  | Datetime | Datetime 值中添加或减去 Integer 或 Double 值，从而返回 Date 值。<br />Datetime myDateTime = Datetime.newInstance(1960, 2, 17); <br />Datetime newDateTime = myDateTime.addDays(2);<br />DateTime myDateTime = DateTime.newInstance(1997, 1, 31, 7, 8, 16); \|<br />[详细参照](https://developer.salesforce.com/docs/atlas.en-us.234.0.apexref.meta/apexref/apex_methods_system_datetime.htm) |
  | Time     | Time myTime = Time.newInstance(1, 2, 3, 4);<br />Time expected = Time.newInstance(4, 2, 3, 4); <br />System.assertEquals(expected, myTime.addHours(3));<br />[详细参照](https://developer.salesforce.com/docs/atlas.en-us.234.0.apexref.meta/apexref/apex_methods_system_time.htm) |
  | Decimal  | 包含小数点的数字。如果不指定小数长度，小数点位置取决于创建赋值时的小数点位置<br />用setScale可以设置小数点位置 <br />Currency自动分配为Decimal |
  | Double   | 包含小数点的 64 位数字。 -2^63 ~ 2^63-1. <br />例：`Double d=3.14159;`不支持 Doubles 的科学记数法 (e)。 |
  | Integer  | 最大32位整数。-2,147,483,648 ~ 2,147,483,647。<br />例：`Integer i = 1;` |
  | Long     | 不包含小数点的 64 位数字。-2^63 ~ 2^63 -1。当您需要比 Integer 提供的范围更宽的值范围时，请使用此数据类型。例:`Long l = 2147483648L;` |
  | ID       | 长度18位<br />如果设置为15位会自动转为18位，因为前三位为sobject识别符<br />例如：`ID id='00300000003T2PGAA0';` |
  | Object   | 所有 Apex 数据类型都继承自 Object;<br />转换：Integer i = (Integer)obj;<br />转换：MyApexClass mc = (MyApexClass)obj; |
  | String   | 不说                                                         |
  | Blob     | 作为单个对象存储的二进制数据的集合。您可以使用以下命令将此数据类型转换为 String 或从 String 和 方法，分别。Blob 可以作为 Web 服务参数被接受，存储在文档中（文档的主体是 Blob），或作为附件发送。 |

---

#### apex heap limits Resolution

[文档](https://help.salesforce.com/s/articleView?id=000328918&type=1)

1. Look for**heap size in debug logs**. If heap size is approaching the limit, investigate it and refactor the code.

2. Use the**'Transient'**keyword with variables. It is used to declare instance variables that cannot be saved,and shouldn’t be transmitted as part of the view state for a Visualforce page.

3. Use**Limit methods**.Use heap limits methods in your Apex code to monitor/manage the heap during execution.

   **Limits.getHeapSize()**– Returns the approximate amount of memory (in bytes) that has been used for the heap in the current context.

   **Limits.getLimitHeapSize()**– Returns the total amount of memory (in bytes) that can be used for the heap in the current context.

   ```
   // check the heap size at runtime
   if (Limits.getHeapSize > 275000) {
        // implement logic to reduce
   }
   ```

4. Reduce heap size during runtime by removing items from the collection as you iterate over it.

5. Use SOQL for loops. To avoid heap size limits, developers should always use a SOQL "for" loop to process query results that return many records.

---

#### Triggers and Order of Execution

要点：



[文档](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_triggers_order_of_execution.htm)

1. Loads the original record from the database or initializes the record for an upsert statement.

2. Loads the new record field values from the request and overwrites the old values.

   If the request came from a standard UI edit page, Salesforce runs system validation to check the record for:

   - Compliance with layout-specific rules
   - Required values at the layout level and field-definition level
   - Valid field formats
   - Maximum field length

   When the request comes from other sources, such as an Apex application or a SOAP API call, Salesforce validates only the foreign keys. Before executing a trigger, Salesforce verifies that any custom foreign keys do not refer to the object itself.

   Salesforce runs custom validation rules if multiline items were created, such as quote line items and opportunity line items.

3. Executes record-triggered flows that are configured to run before the record is saved.

4. Executes all before triggers.

5. Runs most system validation steps again, such as verifying that all required fields have a non-null value, and runs any custom validation rules. The only system validation that Salesforce doesn't run a second time (when the request comes from a standard UI edit page) is the enforcement of layout-specific rules.

6. Executes duplicate rules. If the duplicate rule identifies the record as a duplicate and uses the block action, the record is not saved and no further steps, such as after triggers and workflow rules, are taken.

7. Saves the record to the database, but doesn't commit yet.

8. Executes all after triggers.

9. Executes assignment rules.

10. Executes auto-response rules.

11. Executes workflow rules. If there are workflow field updates:

    1. Updates the record again.
    2. Runs system validations again. Custom validation rules, flows, duplicate rules, processes, and escalation rules are not run again.
    3. Executes before update triggers and after update triggers, regardless of the record operation (insert or update), one more time (and only one more time)

12. Executes escalation rules.

13. Executes the following Salesforce Flow automations, but not in a guaranteed order.

    - Processes
    - Flows launched by processes
    - Flows launched by workflow rules (flow trigger workflow actions pilot)

    When a process or flow executes a DML operation, the affected record goes through the save procedure.

14. Executes entitlement rules.

15. Executes record-triggered flows that are configured to run after the record is saved.

16. If the record contains a roll-up summary field or is part of a cross-object workflow, performs calculations and updates the roll-up summary field in the parent record. Parent record goes through save procedure.

17. If the parent record is updated, and a grandparent record contains a roll-up summary field or is part of a cross-object workflow, performs calculations and updates the roll-up summary field in the grandparent record. Grandparent record goes through save procedure.

18. Executes Criteria Based Sharing evaluation.

19. Commits all DML operations to the database.

20. After the changes are committed to the database, executes post-commit logic such as sending email and executing enqueued asynchronous Apex jobs, including queueable jobs and future methods.

---

#### External Object Relationships

[参考文档](https://help.salesforce.com/s/articleView?id=sf.external_object_relationships.htm&type=5)

| RELATIONSHIP    | ALLOWED CHILD OBJECTS              | ALLOWED PARENT OBJECTS | PARENT FIELD FOR MATCHING RECORDS                            |
| :-------------- | :--------------------------------- | :--------------------- | :----------------------------------------------------------- |
| Lookup          | Standard<br />Custom<br />External | Standard<br />Custom   | The 18-character Salesforce record ID                        |
| External lookup | Standard<br />Custom<br />External | External               | The External ID standard field                               |
| Indirect lookup | External                           | Standard<br />Custom   | You select a custom field with the `External ID` and `Unique` attributes |

---

#### Standard Lightning Page Components

常用的

- List View Component
- Rich Text Component
- Visualforce Page Component
- Report Chart Component

不是的 容易误解的 考试常出现

- Dashboard 

[文档](https://help.salesforce.com/s/articleView?id=sf.lightning_page_components.htm&type=5)

- Accordion
- Actions & Recommendations Component
- Activities
- After Conversation Work (Beta)
- App Launcher Component
- C360 Global Profiles
- C360 Order History
- Call Recording Player
- Chatter Component
- Chatter Feed Component
- Chatter Publisher Component
- Conversation Body
- Customer Experience Score (Pilot)
- Dynamic Actions Bar Component (Pilot)
- Einstein Field Recommendations Component
- Einstein Next Best Action Component
- Einstein Predictions Component
- Einstein Replies Component
- Highlights Panel Component
- Event Insights Component
- List View Component
- Order Product Summaries by Recipient Component
- Order Summary Totals
- Phone
- Quip Document Component
- Rebate Types Panel Component
- Rebate Types Tab Component
- Recent Items Component
- Record Detail Component
- Related List - Single Component
- Related List Quick Links Component
- Related Record Component
- Report Chart Component
- Rich Text Component
- Salesforce Surveys Component
- Send Email Later - Pending List
- Tableau CRM Dashboard Component
- Tabs Component
- Twitter Component
- Visualforce Page Component
- Wave Dashboard Component

---

#### 定数

```
static final Integer PRIVATE_INT_CONST = 200;
```

Extending a Class

```java
public virtual class Marker {
    public virtual void write() {
        System.debug('Writing some text.');
    }

    public virtual Double discount() {
        return .05;
    }
}

// Extension for the Marker class
public class YellowMarker extends Marker {
    public override void write() {
        System.debug('Writing some text using the yellow marker.');
    } 
}

Marker obj1, obj2;
obj1 = new Marker();
// This outputs 'Writing some text.'
obj1.write();

obj2 = new YellowMarker();
// This outputs 'Writing some text using the yellow marker.'
obj2.write();
// We get the discount method for free
// and can call it from the YellowMarker instance.
Double d = obj2.discount();
```



---

#### Custom Button or Link Edit

**Content Source**

- URL
- VisualPage
- onClick javascript

---

#### Schema.DescribeSObjectResult

[文档](https://developer.salesforce.com/docs/atlas.ja-jp.apexcode.meta/apexcode/apex_methods_system_sobject_describe.htm)

获取SObject情报

```java
// 方法1
// Schema.SObjectType.sObjectAPI名
Schema.DescribeSObjectResult describeSObjectResult = Schema.SObjectType.Account;

// 方法2 sObjectAPI名.getSObjectType().getDescribe();
Schema.DescribeSObjectResult describeSObjectResult1 = Account.SObjectType.getDescribe();
Schema.DescribeSObjectResult describeSObjectResult2 = Account.getSObjectType().getDescribe();
Schema.DescribeSObjectResult describeSObjectResult3 = (new Account()).getSObjectType().getDescribe();

// DescribeSObjectResult中有很多方法得到更详细的信息 详细可参照文档
describeSObjectResult.fields();
describeSObjectResult.getSobjectType();
describeSObjectResult.getName();
List<Schema.RecordTypeInfo> recordTypeInfos =  describeFieldResult.getRecordTypeInfos();
```



---

#### Schema.DescribeFieldResult

[文档](https://developer.salesforce.com/docs/atlas.en-us.apexref.meta/apexref/apex_methods_system_fields_describe.htm)

获取Field的情报

```java
// 方法1
// Account.字段API名.getDescribe()
Schema.DescribeFieldResult describeFieldResult = Account.CleanStatus.getDescribe();

// 方法2 Schema.SObjectType.sObjectAPI名.fields.字段API名
Schema.DescribeFieldResult describeFieldResult = Schema.SObjectType.Account.fields.Name;
System.debug(describeFieldResult);

// describeFieldResult中有很多方法得到更详细的信息 详细可参照文档
describeFieldResult.getLabel();
describeFieldResult.getName();
List<Schema.PicklistEntry> plist = describeFieldResult.getPicklistValues();
```

---

#### SOSL 

Valid SearchGroup Settings

| SearchGroup    | Description                                                  |
| :------------- | :----------------------------------------------------------- |
| ALL FIELDS     | Search all searchable fields. If the IN clause is unspecified, then ALL FIELDS is the default setting. |
| EMAIL FIELDS   | Search only email fields.                                    |
| NAME FIELDS    | Search only name fields for standard objects.In addition to the Name field, Salesforce searches the following fields when using IN NAME FIELDS with these standard objects:Account: Website, Site, NameLocalAsset: SerialNumberCase: SuppliedName, SuppliedCompany, SubjectContact: AssistantName, FirstNameLocal, LastNameLocal, AccountNameEvent: SubjectLead: Company, CompanyLocal, FirstNameLocal, LastNameLocalNote: TitlePermissionSet: LabelReport: DescriptionTagDefinition: NormNameTask: SubjectUser: CommunityNicknameIn custom objects, fields that are defined as “Name Field” are searched. In standard and custom objects, name fields have the nameField property set to true. (See the Field array of the fields parameter of the DescribeSObjectResult for more information.) |
| PHONE FIELDS   | Search only phone number fields.                             |
| SIDEBAR FIELDS | Search for valid records as listed in the Sidebar dropdown list. Unlike search in the application, the asterisk (*) wildcard isn’t appended to the end of a search string. |

## Examples of IN Clauses

| Search Type     | Examples                                     |
| :-------------- | :------------------------------------------- |
| No search group | FIND {MyProspect}                            |
| ALL FIELDS      | FIND {MyProspect} IN ALL FIELDS              |
| EMAIL FIELDS    | FIND {mylogin@mycompany.com} IN EMAIL FIELDS |
| NAME FIELDS     | FIND {MyProspect} IN NAME FIELDS             |
| PHONE FIELDS    | FIND {MyProspect} IN PHONE FIELDS            |
| SIDEBAR FIELDS  | FIND {MyProspect} IN SIDEBAR FIELDS          |
| Invalid search  | FIND {MyProspect} IN Accounts                |

请注意，SOSL无法搜索这些对象或字段类型：

●  定义为不可搜索的字段。 您可以通过调用其describeSOjects( )方法并检查名为searchable的属性的值来查询此属性的对象。

●  数字，日期和复选框字段。

●  除非您为搜索组指定“所有字段”，否则不会搜索textarea字段。

● 某些标准对象的某些附件记录。

---

Apex は、次を使用してリリースできます。

[文档](https://developer.salesforce.com/docs/atlas.ja-jp.apexcode.meta/apexcode/apex_deploying.htm)

- [変更セット](https://developer.salesforce.com/docs/atlas.ja-jp.apexcode.meta/apexcode/apex_deploying_changesets.htm)
  - Sandbox-Production等相关组织中
  - Setup中进行配置部署
- [Visual Studio Code 向け Salesforce 拡張機能](https://developer.salesforce.com/docs/atlas.ja-jp.apexcode.meta/apexcode/apex_deploying_ide.htm)
  - 可用于不同组织
- [Ant 移行ツール](https://developer.salesforce.com/docs/atlas.ja-jp.apexcode.meta/apexcode/apex_deploying_ant.htm)
  - Script部署，可用于不同组织
- [SOAP API](https://developer.salesforce.com/docs/atlas.ja-jp.apexcode.meta/apexcode/apex_deploying_additional.htm)
  - Script部署，可用于不同组织
- メタデータ API または Tooling API を使用するサードパーティツール
  - 可用于不同组织
- Salesforce DX プラグインを搭載した VS Code
  - 可用于不同组织
- 管理されていないパッケージ

---

#### ApexPages

- **[addMessage(message)](https://developer.salesforce.com/docs/atlas.ja-jp.pages.meta/pages/apex_System_ApexPages_addMessage.htm)** 現在のページのコンテキストにメッセージを追加します

- **[addMessages(exceptionThrown)](https://developer.salesforce.com/docs/atlas.ja-jp.pages.meta/pages/apex_System_ApexPages_addMessages.htm)** 発生した例外に基づいて、現在のページのコンテキストにメッセージのリストを追加します。

- **[currentPage()](https://developer.salesforce.com/docs/atlas.ja-jp.pages.meta/pages/apex_System_ApexPages_currentPage.htm)**  現在のページの PageReference を返します

- getMessages()

- hasMessages()

- hasMessages(severity)

  

###### PageReference

- インスタンス化
  - ```PageReference pageRef = new PageReference('partialURL');```
  - ```PageReference pageRef = new PageReference('fullURL');```
  - ```PageReference pageRef = new PageReference('http://www.google.com');```
  - ```PageReference pageRef = ApexPages.currentPage();```

- メソッド

  - getParameters()

  - getUrl()

  - getHeaders()

  - setRedirect(redirect)

    

###### StandardController

- 实例化

  - ApexPages.StandardController sc = new ApexPages.StandardController(sObject);

    ```java
    public class myControllerExtension {
    
        private final Account acct;
        
        // The extension constructor initializes the private member
        // variable acct by using the getRecord method from the standard
        // controller.
        public myControllerExtension(ApexPages.StandardController stdController) {
            this.acct = (Account)stdController.getRecord();
        }
    
        public String getGreeting() {
            return 'Hello ' + acct.name + ' (' + acct.id + ')';
        }
    }
    ```

- 方法
  - save()  戻り値 System.PageReference
  - getRecord() 戻り値 sObject
  - view() 戻り値 System.PageReference

---

