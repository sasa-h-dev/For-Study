A developer needs to create a service that will process an email sent to it and create an account and contact using the contents of the email as data for the records.How might a developer accomplish this requirement?Choose one answer
A. Use the Apex Inbound Email Handler.
B. Use the Fuel API with Email Data Extensions.
C. Use Heroku Data Clips to Process Email.
D. Use Auto-launched Flow and Process Builder.	A
How can Apex be used with Visual Workflow?Choose one answer
A. To set the version of a Flow being run.
B. To start a Flow automatically.
C. To add custom styling to a Flow.
D. To control access to a Flow.	B
An integration user makes a successful login() call via the SOAP API.What can be used in the SOAP header to provide server authorization for subsequent API requests?Choose one answer
A. Named Credentials
B. Session ID
C. OAuth access token
D. Security token	B
A customer has a single Visualforce page that allows each user to input up to 1500 sales forecasts and instantly view pivoted forecast calculations. Users are complaining that the page is loading slowly, and they are seeing error messages regarding heap and view state limits. What are three recommendations to optimize page performance?Choose three answers
A. Segregate calculation functionality from input functionality.
B. Specify the list of sales forecasts as transient.
C. Implement pagination and reduce records per page.
D. Create formula fields to compute pivoted forecast calculations.
E. Use JavaScript Remoting instead of controller actions.	A,C,E
A developer is creating unit tests for code that makes SOAP web service callouts. The developer needs to insert some test data as a part of the unit tests setup. What are three actions to enable this functionality?Choose three answers
A. Surround the callout with Test.startTest(), Test.stopTest()
B. Surround the data insertion with Test.startTest(), Test.stopTest().
C. Implement the WebServiceMock interface.
D. Update code to call Test.setMock().
E. Implement the HttpCalloutMock interface.	A,C,D
Which are relevant pratices while analyzing the timeline of different types of transactions in the execution overview panel? Choose 2
A. Log lines in the execution log panel can be analyzed for details about specific events
B. The performance tree shuld beuse dto analyze events further starting from the one that take the least amount of time
C. The execution tree can be used with the execution log to filter and get specific information about events
D. Multiple short busts of Apex events should be analyzed since they can add up to a significant amount of time	A,D
The progress of an apex job queued is using the System.enqueueJob method and needs to be monitored. Which are valid option
A. Use the Apex Jobs page in setup
B. Query the Queueable Apex record
C. Query the AsyncApexJob record
D. Use the Scheduled jobs page in setup	A,C
What are the main differences between a Developer and a Developer Pro Sandbox?Choose 2 answers.
A. Size - 200 MB for a Developer Sandbox, 1 GB for a Developer Pro Sandbox.
B. Refresh Interval - 1 day for a Developer Sandbox, 5 days for a Developer Pro Sandbox.
C. Templates and Sampling - No for a Developer Sandbox, yes for a Developer Pro.
D. Bundled Developer Sandboxes - N/A for a Developer Sandbox, 5 for a Developer Pro Sandbox	A,D
Which of the following statements are true?Choose 2 answers.
A. The refresh interval for a Partial Copy Sandbox is 5 days and the refresh interval for a Full Copy Sandbox is 29 days.
B. A Full Sandbox supports both Templates and Sampling.
C. A Developer Pro Sandbox copies data.
D. A Full Sandbox has 15 Bundled Developer Sandboxes.	A,D
True/False: Sandbox Templates are only available in Partial Copy and Full Sandboxes.	True
It is recommended to load a small set of representative data into Developer and Developer Pro Sandboxes for testing. Which tools can be used for this purpose?Choose 2 ansers.
A. Sandbox template editor.
B. Data Sampling
C. Data Loader
D. Force.com Bulk API	C,D
Which of the following statements are true when refreshing a Sandbox?Choose 3 answers.
A. All licenses are copied from Production.
B. Email delivery defaults to off.
C. Unit tests fail when Messaging.sendEmail throws exceptions.
D. All configuration and customization done in the Sandbox is still there.	A,B,C
True/False: All things configured or customized in Salesforce are available through the Metadata API as XML files.	False
Which of the following can be tracked through the Setup Audit Trail?Choose 3 answers.
A. Which Fields where created in the last 90 days.
B. Who deleted a certain class.
C. How many licenses have been freed up over the last 90 days.
D. The names of the Approval Processes created in the last 6 months.	B,C,D
True/False: If you migrate changes that have newer components to an organization that hasn't been upgraded to support them, the deployment fails.	True
Change Sets are best used for:Choose 2 answers.
A. Straight Sandbox to Production deployments
B. Repetitive Deployments using the same parameters.
C. Large deployments with a lot of setup changes.
D. Change management without using a local file system.	A,D
Which of the following statements are true about Change Sets?Choose 3 answers.
A. Metadata can only move between the Sandboxes and Production.
B. Components can be deployed with a Change Set, but not deleted.
C. Because Change Sets are cloud-based, they're not ideal when used with a source control system.
D. Change Sets are the preferred solution for Deployments.	A,B,C
True/False: Quick Deploy can only be used for Metadata API components.	False
Quick deployments are available when which of the following requirements are met?Choose 3 answers.
A. The components have been validated successfully for the target environment within the last four days (96 hours). As part of the validation, Apex tests in the target org have passed.
B. The components have been validated successfully for the target environment within the last day (24 hours). As part of the validation, Apex tests in the target org have passed.
C. If all tests in the org or all local tests are run, overall code coverage is at least 75%, and Apex triggers have some coverage.
D. If specific tests are run with the Run specified tests test level, each class and trigger that was deployed is covered by at least 75% individually.	A,C,D
A10天
Link the following Types of Asynchronous Apex:
1. Future Methods
2. Batch Apex
3. Queueable Apex
4. Scheduled Apex
To its definition:
A. Run large jobs that would exceed normal processing limits.
B. Schedule Apex to run at a specific time.
C. Run in their own thread, and do not start until resources are available.
D. Similar to Future Apex, but provide additional job chaining and allow more complex data types to be used.	1C 2A 3D 4B
Link the following Types of Asynchronous Apex:
1. Future Methods
2. Batch Apex
3. Queueable Apex
4. Scheduled Apex
To its Common Scenario:
A. Daily or weekly tasks.
B. Performing sequential processing operations with external Web services.
C. Web service callout.
D. Data cleansing or achieving of records.	1C 2D 3B 4A
True/False: The number of SOQL queries allowed under the governor limits are tripled for asynchronous Apex from 100 to 300.	False
True/False: Governor limits for asynchronous calls are independent of the limits in the synchronous request that queued the asynchronous request initially.	True
Which of the following statements are True for Future Methods?Choose 3 answers.
A. Future methods are commonly used for making callouts to external webservices.
B. When making a callout in a Trigger it is unnecessary to use a Future or Queueable method.
C. Future Methods must be static void methods.
D. The specified parameters must be primitive data types, arrays of primitive data types, or collections of primitive data types. Future methods can't take standard or custom objects as arguments.	A,C,D
True/False: Callout in a trigger would hold the database connection open for the lifetime of the callout and that is a "no-no" in a multitenant environment.	True
True/False: Future methods are not guaranteed to execute in the same order as they are called. If you need this type of functionality then Queueable Apex might be a better solution.	True
What is wrong with the following syntax:@future (callout=true)public void sendSMSAsync(String from, String to, sObject Account){// more code}Choose 2 answers:
A. Future Methods must be static.
B. Future Methods must only use primitive data types, no objects.
C. It should be @Future instead of @future.
D. Future Methods must return a boolean.	AB
True/False: To test future methods, enclose your test code between the startTest and stopTest test methods. The system collects all asynchronous calls made after the startTest. When stopTest is executed, all these collected asynchronous processes are then run synchronously.	True
Which is true for the mock callout class needed to test Future Method callouts?Choose 3 answers.
A. The mock class must be a @isTest class.
B. The mock class must implement HttpCalloutMock.
C. The mock class must have a method that returns HttpResponce with the needed data and that takes a HttpRequest as parameter.
D. The mock class must be Protected.	ABC
True/False: The syntax for setting a mock class for callouts in a test method is:Test.setMock(ClassName.class, new ClassName());	False
次のように、第 1 引数では HttpCalloutMock.class を渡し、第 2 引数では HttpCalloutMock のインターフェース実装の新しいインスタンスを渡します。
Test.setMock(HttpCalloutMock.class, new YourHttpCalloutMockImpl());
What is true for Future Methods:Choose 2 answers.
A. Future methods can't be used in Visualforce controllers in getMethodName(), setMethodName(), nor in the constructor.
B. You can't call a future method from a future method. Nor can you invoke a trigger that calls a future method while running a future method.
C. The getContent() and getContentAsPDF() methods can be used in methods with the future annotation.
D. You're limited to 100 future calls per Apex invocation.	BC
Each time a Batch Class is invoked, the job is placed on the Apex job queue and is executed as a discrete transaction. What advantages does a discrete transaction have?Choose 2 answers.
A. Every transaction starts with a new set of governor limits, making it easier to ensure that your code stays within the governor execution limits.
B. If one batch fails to process successfully, all other successful batch transactions aren't rolled back.
C. Discrete transactions have higher governor limits than any other type of Asynchronous Apex.
D. Discrete transactions have higher execution limits than any other type of Asynchronous Apex.	AB
What is true for Batch Apex?Choose 2 answers.
A. A Batch Apex class must be global and implement Database.Batchable
B. The Batch Apex start() is called once and always returns an Iterable.
C. The default batch size of data passed to the execute() is 500 records at a time.
D. Batches of records are not guaranteed to execute in the order they are received from the start() method.	AD
What is false for Batch Apex?Choose 1 answer.
A. You can query up to 50 million records with the QueryLocator object from the start() method.
B. You can query up to 50 million records with the Iterable from the start() method.
C. The execute() method takes a reference to the Database.BatchableContext object and a list of sObjects as parameters.
D. The finish() method is generally used for post-processing and is called once after all batches are processed.	B
How is a Batch class invoked?Choose 1 answer.
A. Instantiate the class myBatchObject and then call Database.executebatch(myBatchObject)
B. Simply call Database.execute(MyBatchClass)
C. Instantiate the class myBatchObject and then call myBatchObject.execute
D. Instantiate the class myBatchObject and then call myBatchObject.Database.execute	A
What is true for invoking a Batch class?Choose 3 answers.
A. Database.executebatch(myBatchObject) returns the Id for the Batch job.
B. Optionally Database.execute() takes a second scope parameter to specify the number of records that should be passed into the execute method for each batch.
C. Each batch Apex invocation creates an AsyncApexJob record so that you can track the job's progress.
D. The only way to see Batch jobs are through the Apex Job Queue in Setup.	ABC
What is true for Batch Apex and state?Choose 2 answers.
A. Batch Apex is typically stateful.
B. If you specify Database.Stateful in the class definition, you can maintain state across all transactions.
C. Only instance member variables retain their values between transactions in Stateful Apex.
D. Both instance variables and method variables retain their values between transactions in Stateful Apex.	BC
True/False: The number of records inserted must be less than the batch size of 200 because test methods can execute only one batch total.	True
Which of the following advantages does Queueable Apex have over Future Apex?Choose 3 Answers.
A. Increased Governor and Execution limits.
B. Queueable Apex can take non-primitive types: Such as sObjects or custom Apex types.
C. Monitoring: When you submit your job by invoking the System.enqueueJob method, the method returns the ID of the AsyncApexJob record.
D. Chaining jobs: You can chain one job to another job by starting a second job from a running job.	BCD
True/False: Because queueable methods are functionally equivalent to future methods, most of the time you'll probably want to use queueable instead of future methods.	FALSE
Which is true for Queueable Apex?Choose 3 answers.
A. To use Queueable Apex implement the Queueable Interface, which has on method called execute.
B. Queueable methods are limited to primitive data types (or arrays or collections of primitives)
C. To add a Queueable class to the job queue, instantiate the Queueable class and call ID jobId = System.enqueueJob(myQueueableJob).
D. You can use the job ID to monitor progress, either through the Apex Jobs page or programmatically by queryingAsyncApexJob.	ACD
What is true for Chaining Jobs using Queueable Apex?Choose 3 answers.
A. You can add only one job from an executing job, which means that only one child job can exist for each parent job.
B. The execution of a queued job counts once against the shared limit for asynchronous Apex method executions.
C. You can add up to 50 jobs to the queue with System.enqueueJob in a single transaction.
D. No limit is enforced on the depth of chained jobs in any production or Sandbox environment, which means that you can chain one job to another job and repeat this process with each new child job to link it to a new child job.	ABC
What is false for Scheduled Apex?Choose 1 answers.
A. The Apex Scheduler lets you delay execution so that you can run Apex classes at a specified time. This is ideal for daily or weekly maintenance tasks using Batch Apex.
B. The class implements the Schedulable interface and must implement the only method that this interface contains, which is the schedule method.(正しい:execute)
C. To invoke Apex classes to run at specific times, first implement the Schedulable interface for the class. Then, schedule an instance of the class to run at a specific time using the System.schedule method.
D. The parameter of this method is a SchedulableContext object. After a class has been scheduled, a CronTrigger object is created that represents the scheduled job. It provides a getTriggerId method that returns the ID of a CronTriggerAPI object.	ACD
 Salesforce ユーザインターフェースの [Apex をスケジュール] ページまたは System.schedule メソッドのいずれかを使用してスケジュールを指定します
Schedulable インターフェースには、実装が必要な 1 つのメソッド execute が含まれています
True/False: After you implement a class with the Schedulable interface, use the System.Schedule method to execute it. TheSystem.Schedule method uses the user's timezone for the basis of all schedules, but runs in system mode—all classes are executed, whether or not the user has permission to execute the class.	T
True/False: The System.Schedule method takes two arguments: a CRON expression used to represent the time and date the job is scheduled to run, and the name of the class.	F
System.Schedule メソッドは、ジョブの名前、ジョブの実行予定日時を表すために使用する式、クラスの名前という 3 つの引数を取ります。この式の構文は次のとおりです。
Seconds Minutes Hours Day_of_month Month Day_of_week Optional_year

proschedule p = new proschedule();
 String sch = '0 0 8 13 2 ?';
 system.schedule('One Time Pro', sch, p);
What is True for Scheduled Apex?
A. You can only have 100 scheduled Apex jobs at one time and there are maximum number of scheduled Apexexecutions per a 24-hour period.
B. Scheduled Apex can only be run programmatically.
C. Use extreme care if you're planning to schedule a class from a trigger. You must be able to guarantee that the trigger won't add more scheduled jobs than the limit.
D. Synchronous Web service callouts are not supported from scheduled Apex. To be able to make callouts, make an asynchronous callout by placing the callout in a method annotated with @future(callout=true) and call this method from scheduled Apex. However, if your scheduled Apex executes a batch job, callouts are supported from the batch class.	ACD
Schedulable インターフェースには、実装が必要な 1 つのメソッド execute が含まれています
Salesforce ユーザインターフェースの [Apex をスケジュール] ページまたは System.schedule メソッドのいずれかを使用してスケジュールを指定します
What is False for the Flex Queue?
A. Future Jobs can be seen in the Flex Queue like any other async job.
B. Apex Flex queue enables you to submit up to 100 batch jobs for execution. Any jobs that are submitted for execution are in holding status and are placed in the Apex Flex queue. Up to 100 batch jobs can be in the holding status.
C. Jobs are processed first-in first-out—in the order in which they're submitted. You can look at the current queue order and shuffle the queue
D. The system can process up to five queued or active jobs simultaneously for each organization. The status of these moved jobs changes from Holding to Queued.	B
What is True for Apex REST Callouts?Choose 3 answers.
A. REST Callouts consists of a HTTP method (Like GET) a URI (the endpoint address) and other optional properties.
B. When the server processes the request, it sends a status code in the response (Like 200 for success)
C. A request can contain headers that provide more information about the request, such as the content type.
D. We should only use REST Apex when SOAP Apex is impossible.	ABC (D REST コールアウトの他に、Apex は XML を使用して SOAP Web サービスへのコールアウトを実行することもできます)
True/False: Apex test methods don't support callouts, and tests that perform callouts fail, instead you have to mock the callout.	T
True/False: WSDL2Apex automatically generates Apex classes from a WSDL document. You download the web service's WSDL file, and then you upload the WSDL and WSDL2Apex generates the Apex classes for you. The Apex classes construct the SOAP XML, transmit the data, and parse the response XML into Apex objects	T
True/False: As you know; to deploy or package Apex code, at least 75% of that code must have test coverage. This coverage does not include classes generated by WSDL2Apex.	F(WSDL2Apex で生成されたクラスも含まれます。)
True/False: When you create an Apex class from a WSDL, the methods in the autogenerated class call WebServiceCallout.invoke, which performs the callout to the external service. When testing these methods, you can instruct the Apex runtime to generate a fake response whenever WebServiceCallout.invoke is called by implementing the WebServiceMock interface and specify a fake response for the testing runtime to send.	T
What is True for Apex REST Webservices.Choose 3 answers.
A. Classes must be global, methods must be global static and be annotated with an HTTP method like @HttpGet.
B. Classes must be annotated with a REST ressource - @RestResource(urlMapping='/Account/*).[sample]
C. The URL mapping is case-insensitive and can't contain a wildcard character (*).
D. The base endpoint for Apex REST is https://yourinstance.salesforce.com/services/apexrest/.	ABD

C(URL 対応付けでは大文字と小文字が区別され、ワイルドカード (*) を含めることができます。)
Each exposed method in an Apex REST Web Service must be defined as global static and add an annotation to associate it with an HTTP method. Link the following @HttpMethods:
1. @HttpGet
2. @HttpPost
3. @HttpDelete
4. @HttpPut
5. @HttpPatch
To its definition:
A. Typically used to update fields in existing records.
B. Reads or retrieves records.
C. Creates records.
D. Deletes records.
E. Typically used to update existing records or create records	1B 2C 3D 4E 5A
True/False: To expose a class as a SOAP Web Service: Define your class as global. Add the webservice keyword and the static definition modifier to each method you want to expose. The webservice keyword provides global access to the method it is added to.	T
What does the following query return?
Choose 1 answer.
SELECT Name, customfield__c, (SELECT OldValue, NewValue FROM foo__history) FROM foo__c
A. Returns every history row for Foo__c and displays the name and custom fields of Foo.
B. Returns every Foo object row together with the corresponding history rows in nested subqueries.
C. The query is invalid.	
Which of the following statements about convertCurrency() in SOQL are True:Choose 2 answers.
A. convertCurrency(field) in the SELECT statement of a SOQL query converts currency fields to the user's currency.
B. FORMAT(field) in the SELECT statement of a SOQL query converts currency fields to the user's currency.
C. It is possible to use convertCurrency in a WHERE clause or in collaboration with ORDER BY.
D. You can't convert the result of an aggregate function into the user's currency by calling the convertCurrency() function.	この構文を RETURNING 句で使用します。
convertCurrency() 関数は WHERE 句では使用できません。
順序は、レポートの場合と同様に、必ず換算後の通貨の値に基づきます。したがって、convertCurrency() と ORDER BY 句は一緒に使用できません。

SOSL クエリに convertCurrency() を使用します

SOQL クエリの SELECT ステートメントで convertCurrency() を使用します
ユーザの地域に従って通貨の書式を設定するには、SELECT() ステートメントで FORMAT() を使用します。
AD
Defines tooltips which appear on mouse over of data series elements. This component offers more configuration options than the default tooltips displayed by setting the tips attribute of a data series component to true. Note: This component must be enclosed by a data series component (, , or ).

A. apex:actionSupport
B. apex:componentBody
C. apex:actionFunction
D. apex:chartTips	D
What name identifies datatypes such as Integer, Boolean, String and Enum in Salesforce?
A. Primitive
B. @ReadOnly
C. Trigger.new
D. FALSE	A
What two forms of dml operations can be used in apex?
A. SOQL statements
B. Traditional for loops
C. Standalone, database class methods
D. Failure response settings	C
Apex offers two ways to perform DML operations: using DML statements or Database class methods.
Each setSavepoint() and rollback statement counts against the total number of DML statements?	True
What term indicates that Salesforce is a platform which allows clients to share hardware, storage and other infrastructure?
A. System
B. On-demand
C. TRUE
D. Multi-tenant	D
What two methods of customization are available to create applications in salesforce?
A. Declarative, programmatic
B. Dates, Ids, Numbers
C. Database class method
D. A governor limit	A
Which fields are returned by sosl by default?
A. Ids
B. 200
C. 6
D. 1	A
What is the list of steps to match regular expressions using the Pattern and Matcher classes?
A. A template from which objects are created
B. Instantiate a pattern object from the expression you wish to match, Instantiate a matcher object from the pattern that contains the string you want to check, Use the matcher object to detect if the matcher matches the pattern.
C. HTTPRequest. HTTPResponse, HTTP
D. Primitive, sObject, Collections, Null	B
What is the this keyword used to represent?
A. Salesforce ui, force.com ide, runTests web service
B. Methods and attributes of the current instance of a class
C. A template from which objects are created
D. HTTPRequest, HTTPResponse, HTTP	B
Which of the following guidelines are used for creating custom Web Services? (Select all that apply.)
• webservice methods must be static.
• webservice methods cannot be overloaded,
• A system-defined enum can be used anywhere in a webservice method.
• All classes that contain methods defined with the webService keyword must be declared as private.
A. FALSE, they must be static
B. Developer edition production org, Enterprise edition sandbox org
C. Static methods can only be declared in a top-level class definition.
D. webservice methods must be static, webservice methods cannot be overloaded	ABCD
 webservice static
Class global
webservice キーワードを使用して、クラスまたは内部クラスメソッドを定義することはできません

システム定義の列挙型は Web サービスメソッドで使用できません。
SOAP および WSDL では、メソッドのオーバーロードはサポートされません
What does Apex use to record disruptions in code execution?
A. @Readonly
B. Catch
C. Webservice
D. Exceptions	D
What keyword is used to create custom Web Services from an apex method?
A. FALSE
B. TRUE
C. Trigger.new
D. Webservice	D
What components must be deployed manually to the production environment?
A. Queues, time triggers
B. Multi-tenant
C. Constructor
D. Dates, Ids, Numbers	A
In what code is the webservice keyword not allowed to be used?
A. Class, trigger
B. Implicit invocation
C. Code contained in a trigger
D. Queues, time triggers	C
What types of sharing are available to developers to share records?
A. Failure response settings
B. Manual sharing, apex sharing
C. Dates, Ids, Numbers
D. Apex, Visualforce, and APIs	B
List the HTTP classes available in Salesforce?
A. GET, POST, PUT, DELETE
B. Failure response settings
C. Queues, time triggers
D. HTTPRequest, HTTPResponse, HTTP	D
Which environments can developers write code? (Select all that apply.)
• Developer edition production org
• Enterprise edition production org
• Enterprise edition sandbox org
• Professional edition sandbox org
A. Salesforce-generated email address
B. Apex code, Visualforce pages, and controllers
C. Developer edition production org, Enterprise edition sandbox org
D. Encapsulation principles	C
What statements are used to retrieve records from an sObject in the Force.com database?
A. Exceptions
B. On-demand
C. Map, List, Set
D. SOQL statements	D
What is the size of the batches in which triggers execute?
A. No
B. 200
C. FALSE
D. Java	B
What interface does the Apex email handler implement to setup and inbound email service?
A. Messaging.sendEmail
B. Messaging.InboundEmailHandler
C. Encapsulation principles
D. isSuccess, sendEmailError	B
Can apex code be created directly in the production environment?
A. Ids
B. 1
C. 10
D. No	D
What are two ways to invoke a custom web service?
A. Apex process classes
B. A governor limit
C. List of List Objects
D. Ajax toolkit, client program	D
Which trigger context variable cannot be deleted?
A. add Error
B. System
C. @ReadOnly
D. Trigger new	D
What are two key tools to debug code in Salesforce?
A. Dates, Ids, Numbers
B. Logs, anonymous blocks
C. Debug logs, email logs
D. List of List Objects	B
Which trigger context variable is not saved in the after trigger and causes an exception to be thrown?
A. Trigger.new
B. addError
C. Primitive
D. TRUE	A
Which keywords do developers use to handle exceptions in Apex?
A. Through class itself
B. Throw, try, catch, finally
C. Static and final
D. GET, POST, PUT, DELETE	B
Which invocation method occurs when triggers are called by the Force.com platform during the save process?
• Explicit invocation
• Implicit invocation
• Explicit invocation using anonymous blocks
• External API invocation
A. RETURNING
B. Implicit invocation
C. Primitive
D. SOQL for loops	B
How should one prevent soql injection when using dynamic soql?
A. Database class method
B. code contained in a trigger
C. Utilize the String.escapeSingleQuotes(string) method
D. with sharing keyword	C
What components of apex are available to improve the processing of data in Salesforce?
A. Database class method
B. GET, POST, PUT, DELETE
C. Batch apex, apex scheduler.
D. Internal and external	A
What are the three ways to run unit tests?
A. Salesforce ui, force.com ide, runTests web service
B. Dates, Ids, Numbers
C. FALSE, they must be static
D. System-defined, user-defined	A
What is the default return type of a sosl statement?
A. Apex process classes
B. Apex classes
C. List of List Objects
D. SOQL for loops	C
Which trigger context variable allows you to modify field values before they are written to the database in the before trigger?
A. @Readonly
B. RETURNING
C. Webservice
D. Trigger.new	D
How are static methods and attributes access?
A. Map, List, Set
B. Class, trigger
C. Apex classes
D. Through class itself	D
What are the four ways to deploy Apex code?
A. Force.com IDE for developers, force.com migration tool, changesets, third-party tools
B. A template from which objects are created
C. Through Ul, Force.com IDE project
D. Developer edition production org. Enterprise edition sandbox org	A
Which statement is true about an Apex class?
• A class cannot be disabled for profiles.
• An inner class can be nested at multiple levels.
• Static methods can only be declared in a top-level class definition.
• The default access modifier for methods in a class is public.
A. Salesforce-generated email address
B. Manual sharing, apex sharing
C. Static methods can only be declared in a top-level class definition.
D. Make calls to methods using both valid and invalid inputs.	C
Under what profile do Webservice methods execute by default?
A. No
B. FALSE
C. TRUE
D. System	D
What are access modifiers used to implement?
A. Traditional for loops
B. Encapsulation principles
C. Class, trigger
D. Static and final	B
What is the maximum size of a SOAP request or response?
A. 3 MB
B. Ids
C. 10
D. Java	A
How do you call Web Services from external sources?
A. SOAP Web Service Callouts
B. Webservice
C. SOQL for loops
D. SOQL statements	A
What does each email service have for which users can send messages?
A. Code contained in a trigger
B. Salesforce-generated email address
C. Schema Explorer
D. Apex process classes	B
What two ways can classes be created in salesforce?
A. isSuccess, sendEmailError
B. Apex, Visualforce, and APIs
C. Through UI, Force.com IDE project
D. Bounced, discarded, queued	C
The email publisher lets support agents who use Case Feed compose and send email messages to customers. You can customize this publisher to support email templates and attachments. This component can only be used in organizations that have Case Feed and Email-to-Case enabled. Ext JS versions less than 3 should not be included on pages that use this component.
A. apex:pageBlock
B. apex:define
C. apex:component
D. apex:emailPublisher	D
An area of a Visualforce page that demarcates which components should be processed by the Force.com server when an AJAX request is generated. Only the components in the body of the component are processed by the server, thereby increasing the performance of the page.
A. apex:outputLabel
B. apex:actionRegion
C. apexfacet
D. apex:emailPublisher	B
A link that executes an action defined by a controller, and then either refreshes the current page, or navigates to a different page based on the PageReference variable that is returned by the action. A component must always be a child of an <apex:form> component.
To add request parameters to the component, use nested <apex:param> components.

A. apexdataList
B. apexenhancedList
C. apexrcommandLink
D. apex:include	C
A timer that sends an AJAX update request to the server according to a time interval that you specify. The update request can then result in a full or partial page update. You should avoid using this component with enhanced lists.
A. apex:dataList
B. apex:actionPoller
C. apex:inlineEditSupport
D. apex:image	B
A single column in a table. A component must always be a child of an <apex:dataTable> or <apex:pageBlockTable> component.
Note that if you specify an sObject field as the value attribute for the component, the associated label for that field is used as the column header by default. To override this behavior, use the headerValue attribute on the column, or the column s header facet.
A. apex:inputField
B. apex:column
C. apex:inputText
D. apex:insert	B
An HTML input element of type hidden, that is, an input element that is invisible to the user. Use this component to pass variables from page to page.
A. apex:inputHidden
B. apex:actionPoller
C. apex:pageBlockSectionltem
D. apex:enhancedList	A
This tag acts as a placeholder for your dynamic Apex components. It has one required parameter—component Value—which accepts the name of an Apex method that returns a dynamic component.
A. apex:dynamicComponent
B. apex:dataList
C. apex:actionSupport
D. apex insert	A
A data series to be rendered as connected points in a Visualforce chart. At a minimum you must specify the fields in the data collection to use as X and Y values for each point, as well as the X and Y axes to scale against.
Note: This component must be enclosed within an <apex:chart> component.
A. apexpageblockSection
B. apex:inputHidden
C. apex:lineSeries
D. apex:inputSecret	C
A template component that declares a named area that must be defined by an <apex:define> component in another Visualforce page. Use this component with the
<apex:composition> and <apex:define> components to share data between multiple pages.
A. apex:outputText
B. apex:barSeries
C. apex:insert
D. apex:inputFile	C
Defines tooltips which appear on mouse over of data series elements. This component offers more configuration options than the default tooltips displayed by setting the tips attribute of a data series component to true.
Note: This component must be enclosed by a data series component (<apex:barSeries>, <apex:lineSeries>, or <apex:pieSeries>).
A. apex:actionSupport
B. apex:componentBody
C. apex:actionFunction
D. apex:chartTips	D
A message for a specific component, such as a warning or error. If the component is not included in a page, most warning and error messages are only shown in the debug log.
A. apex:message
B. apex:flash
C. apex:detail
D. apex:listViews	A
A component that provides support for invoking controller action methods directly from JavaScript code using an AJAX reguest. A component must be a child of an <apex:form> component.
A. apex:messages
B. apex:actionFunction
C. apex:insert
D. apex:outputField	B
An HTML input element of type checkbox. Use this component to get user input for a controller method that does not correspond to a field on a Salesforce object.
A. apex:dataList
B. apex:inputCheckbox
C. apex:actionPoller
D. apex:componentBody	B
The list view picklist for an object, including its associated list of records for the currently selected view. In standard Salesforce applications this component is displayed on the main tab for a particular object.
See also: <apex:enhancedList>.
A. apex:actionStatus
B. apex:listViews
C. apex:inputText
D. apex:pageBlockButtons	B
A read-only display of a label and value for a field on a Salesforce object. A component respects the attributes of the associated field, including how it should be displayed to the user.
A. apex:actionRegion
B. apex:actionSupport
C. apex:outputField
D. apex:pageBlock	C
A component that creates an input field to upload a file.
Note: The maximum file size that can be uploaded via Visualforce is 10 MB.
A. apexbarSeries
B. apex:inputFile
C. apexcomposition
D. apex:legend	B
This tag allows a custom component author to define a location where a user can insert content into the custom component. This is especially useful for generating custom iteration components. This component is valid only within an <apex:component> tag, and only a single definition per custom component is allowed.
A. apex:facet
B. apexrchart
C. apexinclude
D. apexrcomponentBody	D
An HTML input element of type text. Use this component to get user input for a controller method that does not correspond to a field on a Salesforce object. This component does not use Salesforce styling. Also, since it does not correspond to a field, or any other data on an object, custom code is required to use the value the user inputs.
A. apexmessages
B. apex:dynamicComponent
C. apex:inputText
D. apex:inputField	C
A custom Visualforce component. All custom component definitions must be wrapped inside this component tag.
A. apex:includeScript
B. apexCommandLink
C. apexdataTable
D. apexComponent	D
A Visualforce chart. Defines general characteristics of the chart, including size and data binding.

A. apex:actionSupport
B. apex:inlineEditSupport
C. apexrchart
D. apex:enhancedList	C
A single piece of data in an <apex:pageBlockSection> that takes up one column in one row. A component can include up to two child components. If no content is specified, the column is rendered as an empty space. If one child component is specified, the content spans both cells of the column. If two child components are specified, the content of the first is rendered in the left, "label" cell of the column, while the content of the second is rendered in the right, "data" cell of the column.
A. apex:flash
B. apex:pageBlockSectionltem
C. apex:outputField
D. apex:componentBody	B
The standard detail page for a particular object, as defined by the associated page layout for the object in Setup. This component includes attributes for including or excluding the associated related lists, related list hover links, and title bar that appear in the standard Salesforce application interface.
A. apex pageblockSection
B. apexrcomponent
C. apex:insert
D. apex:detail	D
A component that creates an inline frame within a Visualforce page. A frame allows you to keep some information visible while other information is scrolled or replaced.
A. apex:include
B. apex:iiframe
C. apex:chartLabel
D. apex:attribute	B
Defines how labels are displayed. Depending on what component wraps it, this compoment gives you options for affecting labels for bar and line series labels, pie chart segments, and axes labels.
Note: This component must be enclosed by a data series component (<apex:barSeries>, <apex:lineSeries>, or <apex:pieSeries>) or an <apex:axis> component.
A. apex:chart
B. apex:include
C. apexrchartLabel
D. apex:messages	C
A data series to be rendered as bars in a Visualforce chart At a minimum you must specify the fields in the data collection to use as X and V values for each bar, as well as the X and Y axes to scale against.
Note: This component must be enclosed within an <apex:chart> component. You can have multiple <apex:barSeries> and <apex:lineSeries> components in a single chart.
A. apexrbarSeries
B. apex:inputHidden
C. apex:outputLink
D. apexoutputField	A
A link to a JavaScript library that can be used in the Visualforce page. When specified, this component injects a script reference into the head element of the generated HTML page. For performance reasons, you may simply want to use a JavaScript tag before your closing <apex:page> tag, rather than this component.
A. apex:includeScript
B. apex:outputField
C. apex:attribute
D. apex:component	A
A section of data within an <apex:pageBlock> component, similar to a section in a standard Salesforce page layout definition.
A component consists of one or more columns, each of which spans two cells: one for a field's label, and one for its value. 
A. apex:outputLabel
B. apex:actionPoller
C. apex:pageblockSection
D. apex:facet	C
A set of buttons that are styled like standard Salesforce buttons. This component must be a child component of an <apex:pageBlock>.
A. apex:includeScript
B. apex:commandButton
C. apex:pageBlockButtons
D. apex:form	C
A text area input element. Use this component to get user input for a controller method that does not correspond to a field on a Salesforce object, for a value that requires a text area.
A. apex:inputTextarea
B. apex:facet
C. apex:include
D. apex:attribute	A
A section of a Visualforce page that allows users to enter input and then submit it with an <apex:commandButton> or <apex:commandLink>. The body of the form determines the data that is displayed and the way it is processed. 
As of API version 18.0, this tag can t be a child component of <apex:repeat>.
A. apex:form
B. apex:chart
C. apex:actionRegion
D. apex:insert	A
A single Visualforce page. All pages must be wrapped inside a single page component tag.
A. apex:insert
B. apex:page
C. apex:axis
D. apex:outputLabel	B
An HTML input element of type password. Use this component to get user input for a controller method that does not correspond to a field on a Salesforce object, for a value that is masked as the user types.
A. apex:composition
B. apex barSeries
C. apex:inputSecret
D. apex:attribute	C
An area of a page that uses styling similar to the appearance of a Salesforce detail page, but without any default content.
A. apex:pageBlock
B. apex:commandLink
C. apex include
D. apex:chartTips	A
A button that is rendered as an HTML input element with the type attribute set to submit, reset, or image, depending on the this component tag's specified values. The button executes an action defined by a controller, and then either refreshes the current page, or navigates to a different page based on the PageFteference variable that is returned by the action.
An <apex:commandButton> component must always be a child of an <apex:form> component. See also: <apex:commandLink>
A. apex:commandButton
B. apex:flash
C. apex:emailPublisher
D. apex:actionRegion	A
A Flash movie, rendered with the HTML object and embed tags
A. apex:actionStatus
B. apex:flash
C. apex:inputField
D. apex:pageBlockSectionltem	B
An ordered or unordered list of values that is defined by iterating over a set of data. The body of the component specifies how a single item should appear in the list. The data set can include up to 1.000 items.
A. apex:inputText
B. apex:dataList
C. apex:lineSeries
D. apex:inputCheckbox	B
A template component that provides content for an <apex:insert> component defined in a Visualforce template page. See also: <apex:composition>, <apex:insert>
A. apex:facet
B. apex:includeScript
C. apex:axis
D. apex:define	D
The Log a Call publisher lets support agents who use Case Feed create logs for customer calls. This component can only be used in organizations that have Case Feed, Chatter, and feed tracking on cases enabled.
A. apex:inputHidden
B. apexi:frame
C. apex:chartLabel
D. apex:doCallPublisher	D
A component that displays the status of an AJAX update request. An AJAX request can either be in progress or complete.
A. apex:actionPoller
B. apex:dynamicComponent
C. apex:inputCheckbox
D. apex:actionStatus	D
A link to a URL. This component is rendered in HTML as an anchor tag with an href attribute. Like its HTML equivalent, the body of an <apex:outputLink> is the text or image that displays as the link. To add query string parameters to a link, use nested <apex:param> components.
A. apex:inputField
B. apex:outputLink
C. apex:lineSeries
D. apex:emailPublisher	B
A component that adds AJAX support to another component, allowing the component to be refreshed asynchronously by the server when a particular event occurs, such as a button click or mouseover.
See also: <apex:actionFunction>.
A. apex:form
B. apex:attribute
C. apex:page
D. apex:actionSupport	D
Like other Apex classes, custom controllers execute entirely in ____________, in which the object and field- level permissions of the current user are ignored.

A. User Mode
B. System Mode
C. OWD Mode
D. With-Sharing Mode
E. Anonymous Mode
F. None of the above	B
A developer needs to compile a list for all Accounts and Opportunities that have the word "Acme" in their name' and are created today. Which statement provides the developer with the result?

A. FIND "Acme" IN NAME FIELDS RETURNING Account (Id), Opportunity (Id) WHERE CreatedDate TODAY
B. SELECT Id, AccountId FROM Opportunity WHERE CreatedDate = TODAY AND ( Name LIKE '%Acme'a'
Account.Name LIKE '%Acme%'
C. SELECT Id, ( SELECT Id FROM Opportunities WHERE CreatedDate = TODAY ) FROM Account WHERE
" CreatedDate = TODAY AND Name LIKE '%Acme%'
D. FIND "Acme"IN NAME FIELDS RETURNING Account (Id WHERE CreatedDate = TODAY), Opportunity (Id
WHERE CreatedDate = TODAY)	D
A custom field Exec_Count_c of type Number is created on an Account object. An account record with value of "1" for a: Exec_Count_c is saved. A workflow field update is defined on the Exec_Count_c field, to increment its value every time an account record is created or updated. The following trigger is defined on the account: trigger ExecOrderTrigger on Account (before insert, before update, after insert, after update) { for (Account accountInstance: Trigger.New) { if (Trigger . isBefore) { accountInstance . Exec_Count_c +=l; System. debug (accountInstance . Exec_Count_c); } } } What is printed from the System.debug statement? Output from System.debug in every iteration is separated with a delimiter.

A. 1,2,3,3
B. 1,2,3,4
C. 2,2,4,4
D. 2,2,3,3	C
A developer writes the following Apex trigger so that when a Case is closed, a single Survey record is created for that Case. The issue is that multiple Survey-c records are being created per Case. trigger CaseTrigger on Case (after insert, after update) { List createSurveys = new List(); for (Case c : trigger.new) { if (c.IsClosed && (trigger.isInsert ll trigger.isUpdate && trigger.oldMap.get(c.Id).IsClosed == false)) { createSurveys.add(new Survey c(Case c = c.Id)); insert createSurveys; } } What could be the cause of this issue?
A. A user is creating the record as Closed
B. A workflow rule is firing with a Create Task action.
C. A workflow rule is firing with a Field Update action.
D. A user is editing the record multiple times.	C
Which statement is true about scheduled Apex? Choose 3 answers
A. The schedule of an Active scheduled Apex class cannot be updated through the Salesforce User Interface.
B. Scheduled Apex is executed only when system resources are available.
C. Scheduled Apex only supports asynchronous callouts through the use of @future methods and Apex
Batches.
D. Scheduled Apex classes can only be defined by extending the Schedule base class.
E. There is no limit on Scheduled Apex jobs because they are executed asynchronously	A,B,C
JavaScript remote actions need be either a _______ or _______ class and must be _______.

A. Public or global and must be static.
B. Private or global and must be static.
C. Public or TestVisible and must be static.	A
A developer receives a LimitException: Too many query rows: 50001 error when running code. What debugging approach using the Developer Console provides the fastest and most accurate machanism to identify a specific component that may be returning an expected number of rows?

A. Count the number of Row Limit warning messages in the Debug Logs.
B. Add System.debug (System.getoueryRows () to the code to track SOQL usage.
C. Filter the Debug Log on SOQL_EXECUTE_END statements to track the results of each SOQL Query.
D. Use the Execution Overview to see the number of rows returned by each Executed Unit.	C
A Salesforce developer created a Contact validation rule so that the Email field cannot contain "abc.com." There is an active workflow rule that updates the Email field of a contact record to "test@abc.com" if the contact's First Name field contains the word "Test.
A customer tries to create a Contact record with the first name "Test Contact" and the 
email "test@test.com." What behavior will be observed ?
A. The customer will receive a system error message.
B. The contact record will be created with the email address "test@abc.com. "
C. The customer will receive a validation error message.
D. The contact record will be created with the email address test@test.com.	B
A developer would like to use jQuery in a Visualforce page.
Which markup can be used to load the library on the page?
A. <apex:include value="{ !$Resource.jQuery}"
B. <apex:includeScript value="{ !$Resource.jQuery }
C. <apex: script value="{ l$Resource.jQuery}
D. <apex:includeJS value="{ !$Resource.jQuery} - Wrong. No tag exists as such	B
What is the <apex:actionSupport> tag used for in Visualforce pages?
A. To provide help and support content for buttons and links.
B. To trigger a second action when a button or link is clicked.
C. To trigger controller actions in response to DOM element events.
D. To create a Javascript function that can trigger a controller action	C
A developer has created the following trigger:
trigger ProcessDoNotCall on Contact (after update)
List<Contact> lstCon = [SELECT Id, DoNotCall, Department FROM ContactWHERE Department = 'HR' AND Id IN :Trigger.new];
for(Contact c : lstCon)
c.DoNotCall= true;
update lstCon;
The developer executes the following code anonymously in the Developer Console. Assume that the record exists in Salesforce.
Contact con = new Contact(Id='003oOOOOOOVHXOm',Department = 'HR');
update con;
Which behavior will the developer observe?
A. The code will throw an exception because the maximum trigger depth has been exceeded.
B. The code will throw an exception, saying that the record cannot be updated in an After Update trigger.
C. The code will throw an exception in Anonymous Apex, indicating that the Id field is read-only. [ Not correct ]
D. The contact record will be saved and the contact record's DoNotCall field will be set to true.	A
A developer has written a Visualforce page to create a new account with the following markup:
<apex:inputfield value="{!newAccount.website}"/>
The Visualforce page has extra logic for validating the website field. How can the developer add an error message next to the website field if the submitted value isn't valid?
A. Use Account.fields.website.addError(message)
B. Use throw new SObj ectException(message)
C. Use Account.website.addError(message)
D. Use ApexPages.addMessage(message)	C
A developer has created an Order entry page that includes an <apex:outputLabel> tag for a field label.
How can the developer ensure that the label text changes when the field label changes?
A. Use FieldSetMember methods to control label text.
B. Use the SObjectType variable to control label text.
C. Use a custom label to manage the label text.
D. Use the metadata API to update the label text.	B
A developer has created a Batchable class that inserts Accounts.
The Batchable class is running with a batch size of 200, and is getting an error.
The developer identifies the following code as problematic.
trigger AccountTrigger on Account(after insert)
for( Account a : Trigger.new
AccountHandler.insertPartnerAccount(a);
public Class AccountHandler{
@future
public static void insertPartnerAccount(Account a){
perform processing
if( a.Is_Partner__c)
Account partnerAccount = new Account();
set values
insert partnerAccount;
}
}
What governor limit or system limitation is the developer most likely violating?
A. Too many DML statements in the batch execution context.
B. Maximum trigger depth exceeded on the Account insert.
C. Too many future calls in the batch execution context.
D. Future method cannot be called from a batch method.	D
A developer needs to write tests to ensure that code doesn't fail when it is deployed to a different organization.
The developer also must ensure that the code works properly with organization sharing rules and ensure that the code mitigates errors due to limits.
How can the developer meet these requirements? Choose 2 answers
A. Create all test data before calling the Test. startTest () and Test .stopTest () methods.
B. Handle all exceptions that are caught by adding an empty catch ( Exception e) statement.
C. Use SeeAllData=true to avoid delaying tests due to creating test data.
D. Use the runAs ( ) method to test the application in different user contexts.	B,D
What is a controller value that will NOT be saved in the viewstate of a Visualforce page?
Choose 3 answers
A. Variable declared with the Transient keyword.
B. A variable of a type that is a collection of SObjects.
C. A system-generated object such as a Schema Describe object.
D. A variable declared with the Static keyword.
E. A variable of a type that is a custom Apex class.	A,C,D
A developer must create a way for external partners to submit millions of leads into Salesforce per day.
How should the developer meet this requirement?
A. Create a web service on Heroku that uses Heroku Connect.
B. Publicly expose a Visualforce page via Force.com Sites.
C. Publicly expose an Apex Web Service via Force.com Sites.
D. Host a Web-to-Lead form on the company website.	A
A developer created a Visualforce page that has a custom controller that navigates to an external website after the' command button is pressed.
What is the recommended way to test this functionality?
A. Use .getURL() on the result of the action method and System.assertEquals () to compare the resulting URL.
B. Use ApexPages.currentPage () .getUrl () and System.assertElquals () to compare the end URL.
C. Use Test.getCurrentPage() .getUrl () and System.assertEquals () to compare the end URL.
D. Test the navigation by executing the use case through the browser and manually inspecting the resulting URL	A
An Apex test method is testing a Visualforce page's controller, which queries for all Opportunities in Salesforce with StageName = 'Closed'.
There are 10,000 existing records that match the criteria.
What is the best practice for accessing data in the test method?
A. Create test data in the test method and use seeAllData=true.
B. Query existing data in the test method and use seeAllData=true.
C. Create test data in the test method and use seeAllData=false.
D. Use @testVisible on the relevant property of the controller	C
In an Apex custom controller, how should a developer ensure that the current user has the relevant create and update' permissions for a particular object type?
A. Call methods on the appropriate DescribeSObjectResult instance.
B. Query the user's profile record and check what permissions the user has.
C. Do nothing because the platform enforces CRUD permissions based on profiles.
D. Add the with sharing keywords to the controller class definition.	A
What is the output of the following code snippet?
l Contact con = new Contact( LastName = 'JOHNSON', LeadSource = 'Web')
2
3 Savepoint sp = Database.setSavepoint();
4 insert con;
5 Database.rollback(sp);
6
7 con.LeadSource = 'Email'
8 insert con;
A. A runtime error will be thrown on line 5.
B. The contact record will be inserted with Leadsource value Web.
C. A runtime error will be thrown on line 8.
D. The contact record will be inserted with Leadsource value Email.	C
To reduce the amount of time needed to write test coverage, a developer wants to use a spreadsheet uploaded as a Static Resource to supply test data in a test method.
What code can the developer use to accomplish this?
A. List<sObj ect> testAccounts = (Listhcount>) [Select Id, Body from StaticResource Where Name = testAccounts
B. List<sObject> testAccounts = Test.loadData (Account.sObjectType, 'testAccounts');
C. List<sObject> testAccounts = Test.loadData (Account.sObjectType, SResource. testAccounts)
D. List<sObj ect> testAccounts = Test.loadData( [Select Id, Body from StaticResource Where Name = testAccounts])	B
What is the top-level namespace that provides the ability to use Chatter in Apex?
A. RestApi
B. ChatterApi
C. FeedApi
D. ConnectApi	D
What type of request and payload format can be received by a static method in a global Apex class that uses the webService keyword?
A. REST/JSON
B. SOAP/XML and SOAP/JSON
C. SOAP/XML and REST/JSON
D. SOAP/XML	D
Which object should be used to access sharing programmatically on an object named Equipment__c?
A. Equipment_Share_c
B. Equipment-c
C. Equipment_c_share
D. Equipment__Share	D
A company has 20,000 rows in the Account object and 2 million rows in the Sales_Data_c object that is related to Account.
All of the records in the Sales_Data_c object have a field that contains the string 'Le.'
Which statement will throw a ""Too many query rows"" exception? Choose 2 answers
A. List<List<SObject>> result= [FIND 'Le' IN ALL FIELDS RETURNING Sales_Data_c(Id)];
B. List<Account> result = [SELECT Id, (SELECT Id FROM Sales_Data_r) FROM Account]
C. List<sObject> result = Database.query('SELECT Id FROM Sales_Data_c LIMIT 50000');
D. List<AggregateResult> result = [SELECT count(Id) total FROM Sales_Data_c];	A,B
What should a developer do to invoke a SOAP web service from Apex? Choose 2 answers
A. Invoke the web service from a trigger.
B. Generate an Apex class from the WSDL.
C. Annotate the method With @future (callout=true)
D. Configure the remote site settings.	B,D
A user updates a number field on a record from the value of 1 to 2, and a workflow rule executes, incrementing the value to 3.
Which statement is true regarding writing triggers in this case?
Choose 2 answers
A. Workflow rules will execute before triggers.
B. Triggers will execute before and after workflow rules.
C. Trigger.old will contain the user entered value of 2.
D. Trigger.old will contain the initial value of 1.	B,D
Trigger on Contact ensures that whenever a Contact's custom field ""User Level"" is given the value ""President,"" the related Community User's Role is updated as Manager.
The Apex unit test method for testing this functionality is failing for a mixed DML error. What is one way that this problem can be solved?
A. Query the user roles before the test method's startTest () statement.
B. Create test data for the roles before startTest 0.
C. Put the update of contact event inside startTest() and stopTest().
D. Use a System. runAs () block to update the contact.	D
What is the potential exception that can be thrown from this SOQL query:
Account a = [SELECT Id, (SELECT Id FROM Contacts) FROM Account]
Choose 2 answers
A. QueryException if no records are returned.
B. QueryException if more than one record is returned.
C. TypeException if a Contact is returned as part of the query.
D. NullPointerException if no records are returned."	A,B
What field type can be used in the WHERE clause to improve SOQL query performance?
Choose 3 answers
A. Email fields
B. Name fields
C. Telephone fields
D. Lookup fields
E. External Id fields	B,D,E
A developer needs to design a custom object that will be integrated into a back-end system.
What should the developer do to ensure good data quality and to ensure that data imports, integrations, and searches perform well?
Choose 2 answers
A. Configure a custom field as indexed.
B. Configure a custom field as Salesforce ID.
C. Configure a custom field as unique.
D. Configure a custom field as external ID.	C,D
A developer has been asked to prevent Accounts from being deleted if there is a related Contact that has the Do_Not_Delete_c checkbox checked.
How can the developer accomplish this?
A. Create a Validation Rule on the Contact object.
B. Create a Before Delete Trigger on the Account object.
C. Create a Validation Rule on the Account object.
D. Create a Before Delete Trigger on the Contact object.	B
What is the recommended approach to create test data when testing Apex that involves Pricebooks, PricebookEntries, and Products?
A. Insert a new standard Pricebook record within your Test Method so that it can be used with other test records.
B Use the Test.getStandardPricebookId() method to get the Id of the standard Pricebook so that it can be used with other test records.
C. Use the isTest (SeeAllDataFtrue) annotation on Test Methods that require access to the standard Pricebook.
D. A Use the isTest (SeeAllData=true) annotation on the entire Test Class to allow your Test Methods access to the standard Pricebook.	B
A developer has refactored an application and renamed an Apex class in a sandbox and now needs to deploy the changes to production.
How can this be accomplished? Choose 2 answers
A. Deploy the new Apex class with the Force.com Migration Tool and set the old name in destructiveChanges.xml.
B. Use a changeset to both delete the old Apex class and deploy the new Apex class to production.
C. Deploy the new Apex class, and then log in to the production environment and manually delete the class.
D. Use the Force.com IDE to delete the old Apex class from the project and deploy the changes to production.	A,D
What can the Apex Continuation class be used for?
A. Chaining multiple Queueable Apex jobs to be processed one after another.
B. Making asynchronous callouts to SOAP or REST Web Services from Visualforce.
C. Maintaining an Apex transaction across multiple DML statements.
D. Progressing records to the next stage of an approval process in Apex.	B
What is the output of the following code snippet?
Contact con = new Contact( LastName = 'Smith', Department = 'Admin')
2 insert con;
3
4 Savepoint sp_finance = Database.setSavepoint();
5 con.Department = 'finance';
6 update con;
7
8 SavepOLnt sp_hr = Database.setSavepo1nt();
9 con.Department = 'HR';
10 update con;
11
12 Database.rollback(3p_flnance);
l3 Database.rollback(3p_hr);
A. The contact record will be saved ME department value HR.
B. A runtime error will be thrown on line 12.
C. A runtime error will be thrown on line 13.
D. The contact record will be saved with department value Finance.	C
A developer needs to create a Visualforce page to override the standard New Contact Button.
The page contains a field of for capturing the Contact's daytime preferred Phone number.
The user has the option to select one of the four available phone types (Mobile, Home, Work, or Other) to be the primary contact number. Only if the ""Other"" Phone Type option is selected, the page must display a text box for the User to provide the other Phone number.
How can this requirement be met? Choose 2 answers
A. Use the rendered attribure on the Other Phone Input text field to control its selective display.
B. Use the apex:rendered tag to enclose the Other Phone input text field to control its selective display.
C. Use the rerender attribute on the Phone Type select Iist's apex:actionsupport to refresh the Other Phone text field.
D. Use apex:actionsupport tag to enclose the Phone Type select list to refresh the Other Phone text field.	A,C
What is the most efficient way in Visualforce to show information based on data filters defined by an end-user for a large volume of data?
A. Use an Apex controller to refine raw data based on data filters and store the result in a transient variable.
B. Use an Apex controller to refine raw data based on data filters and store the result in a snauc variable.
C. Use the rendered condition in Visualforce to limit data based on data filters.
D. Use filter conditions in a SOQL query to limit data based on data filters.	D
How can Apex class functionality be exposed for invocation from a Lightning process?
Choose 2 answers
A. Expose the class as a custom REST API.
B. Use the @InvocableMethod annotation.
C. Extend the ProcessInvocable base class.
D. Implement the Process.Plugin interface.	B,D
What log category should be used to see the limits in the Execution Overview of the Developer Console?
A. System
B. Profiling
C. Apex Code
D. Database	B
A developer needs to create a Lightning page for entering Order Information.
An error message should be displayed if the zip code entered as part of the Order's shipping address is not numeric.
What is a recommended way for the error message be displayed to the end user?
A. Use the ui : outputText tag to display errors.
B. Use the apex:Message tag to display errors.
C. Use the aura:component tag to display errors.
D. Use the ui:inputDefaultError tag to display errors.	D
A company exposes a REST web service and wants to establish two-way SSL between Salesforce and the REST web service.
A certificate signed by an appropriate certificate authority has been provided to the developer.
What modification is necessary on the Salesforce side? Choose 2 answers
A. Create an entry for the certificate in Certificate and Key Management.
B. Configure two-factor authentication with the provided certificate.
c. Update the code to use HttpRequest.setHeader() to set an Authorization header.
D. Update the code to use HttpRequest.setClientCertificateName	A,D
"A developer has created a Visualforce page that uses a third-party JavaScript framework. The developer has decided to supply data to the JavaScript functions using JavaScript Remoting for Apex Controllers.
What is the correct syntax to declare a remote method in Apex? Choose 2 answers
A. @RemoteAction
public static String getTable()
B. @RemoteAction
global String getTable()
C. @RemoteAction
global static String getTable()
D.@Remoteobject
global static String gettable	A,C
What does the System. runAs () method enforce based on the target user?
A. Object CRUD permissions
B. Record sharing
C. Field-level permissions
D. License limits	B
Which statement is true about scheduled Apex? Choose 3 answers
A. The schedule of an Active scheduled Apex class cannot be updated through the Salesforce User Interface.
B. Scheduled Apex is executed only when system resources are available.
C. Scheduled Apex only supports asynchronous callouts through the use of @future methods and Apex Batches.
D. Scheduled Apex classes can only be defined by extending the Schedule base class.
E. There is no limit on Scheduled Apex jobs because they are executed asynchronously	A,B,C
What is a benefit of using list custom settings?
A. Ability to include more field type options than custom objects.
B. Ability to control sharing and visibility of custom setting data.
C. Ability to provide more efficient access than custom objects.
D. Ability to delegate administrator rights to standard users.	C
A developer has created a solution using the SOAP API for authenticating Communities users.
What is needed when issuing the login()Call? Choose 2 answers
A. Organization Id
B. Security Token
C. Session Id
D. Username and Password"	A,D
Which statement is true about Apex web service methods? Choose 3 answers
A. Web service methods can be exposed having a custom Apex class as parameter datatype.
B. Web service methods can be overloaded with methods of the same name in the same class.
C. Web service methods can only be added to Apex classes that are declared global.
D. Web service methods can only be added to Apex triggers that are declared global.
E. Web service methods cannot be deprecated in managed package code.	A,C,E
A developer has created a Visualforce page for inputting data and needs to display errors at the field level. What tag should the developer use?
A. <apexes:messages>
B. <apexzpageMessages>
C. <apex:message>
D. <apex:pageMessage>	C
"A developer must create a custom pagination solution for accessing approximately 2000 records and displaying 50 records on each page. Data from Salesforce will be accessed via an API and not via Apex.
How can the developer meet these requirements? Choose 2 answers
A. Use OFFSET in SOQL queries.
B. Use LIMIT 50 in SOQL queries.
C. Use a StandardSetController.
D. Use CURSOR 50 in SOQL queries.	A,B
Given the following code sample, what is a potential issue regarding bulk processing of records?
trigger accountTestTrggr on Account (before insert, before update)
Account acct = Trigger.new[0];
List <Contact> contacts = new List <Contact> ([select id, salutation, firstname, lastname,
email from Contact where accountId = :acct.Id]);
for (Contact con: contacts)
con.Title = 'Not Selected';
update contacts;
A. The code will not execute because the record in the list can be null and cause an exception.
B. The code will process one record that is called explicitly per execution.
C. The code will not execute because the list can be null and cause an exception.
D. The code will have to be invoked multiple times to process all the records.	D
How could a developer create a Visualforce page for a multi-language organization? Choose 2 answers
A. Use <apex:pageMessages> by default to support translation workbench.
B. Use custom labels to display validation rule errors in the current user's language.
C. Use custom labels to display text in the current user's language.
D. Use the language attribute of <apex:page> to support translation workbench.	C,D
Which object can a developer use to programmatically determine who is following a specific User record in Chatter?
A. EntitySubscription
B. FollowHistory
C. FollowSubscription
D. EntityHistory	A
What is the value of ""i"" printed by the System.debug statement, if the value of "j" is 2 at the end of the transaction?
insert new Account[]{new Account(Name = 'yyy'), new Account(Name = 'yyy')};
integer i = 0;
integer j;
for (Account[] tmp : [SELECT Id FROM Account WHERE Name = 'yyy'])
j=tmp.size();
i++;
System.debug(i);
A. 0
B. 2
C. 1
D. 3	C
What is a technique to maximize code re-use within Visualforce pages? Choose 3 answers
A. Referencing an existing page With (apex: include).
B. Creating Visualforce Templates With <apex:composition>.
C. Defining reusable page regions with <apex:actionRegion>.
D. Creating reusable page sections with <apex:pageBlockSection>.
E. Creating reusable Visualforce Components with <apex:component>.	A,B,E
What is a limitation of a "getxxx" method (for example, getName) in a custom Visualforce controller?
A. The method cannot return SObjects.
B. The method cannot use DML operations.
C. The method cannot return Apex classes.
D. The method cannot use SOSL queries.	B
A company requires that a child custom record is created when an Order record is inserted.
The company's administrator must be able to make changes to the solution.
What is the recommended solution for implementing this requirement?
A. Create a Visual Workflow that will create the custom child record when the Order is inserted.
B. Create a Force.com Workflow Rule to create the custom child record when the Order is inserted.
C. Create an Apex Trigger to create the custom child record when the Order is inserted.
D. Create a Lightning Process to create the custom child record when the Order is inserted.	A
A developer must create a custom pagination solution. Users will access the solution on a mobile device and will rarely access subsequent pages of records. Performance is crucial.
Which approach is optimal?
A. Use OFFSET CURSOR in SOQL queries.
B. Use a StandardSetController.
C. Use @Cache annotation in the controller.
D. Use OFFSET in SOQL queries.	D
When should a developer use the transient keyword? Choose 2 answers
A. To declare an Apex variable as type-less when developing with dynamic Apex.
B. To prevent Apex interface definitions being included in the Apex-based partner WSDL.
C. To prevent Apex controller variables being sent to the Visualforce page as view state.
D. To exclude Apex class variables from getting serialized if they are in a serializable class	C,D
Which tool in the Developer Console can a developer use to monitor the cardinality and the cost of a SOQL query?
A. View State tab
B. Query Plan Tool
C. Audit Log
D. Query Activity Tool	B
Which two objects can be inserted in the same transaction? Choose 2 answers
A. Account and Group
B. Case and CaseComment
C. Opportunity and User
D. Account and AccountShare	B,D
A Visualforce page controller calls an external web service to get a list of records and display them on the page.
The external web service has a complex backend and generally takes a long time to return results, causing timeouts. What can be done to avoid timeouts and display the results without any errors?
A. Use the setTimeout () method on the HttpRequest to increase the timeout of the callout.
B. Create a callback method and create an instance of a Continuation object in an action method.
C. Implement the Batchable interface to perform the callout and capture the response in the batch job.
D. Use the <apex:actionPoller> tag and keep polling to check the status of the response in the controller."	B
A developer is writing a complex application involving triggers, workflow rules, Apex classes, and processes. The developer needs to carefully consider the order of execution when developing the application.
In what order do the following operations execute? 
1. before Triggers
2. after Triggers
3. Post commit logic such as sending email
4. DML committed to the database
5. Workflow rules
6. Roll-up summary calculations
A. 1,2,5,6,4,3
B. 1,5, 6, 2, 4, 3
c. 1, 2, 4, 5,6, 3
D. 1, 6,5,2,4,3	A
A developer has been asked to create code that will meet the following requirements:
Receives input of: Map<Id, Project-c), List<Account>
Performs a potentially long-running callout to an outside web service
Provides a way to confirm that the process executed successfully
Which asynchronous feature should be used?
A. @future (callout=true)
B. Database.AllowsCallouts interface
C. Schedulable interface
D. Queueable interface	D
A developer wants to retrieve and deploy metadata, perform simple CSV export of query results, and debug Apex REST calls by viewing JSON responses.
Which tool should the developer use?
A. Developer Console
B. Force.com Migration Tool
C. Workbench
D. Force.com IDE	C
What is a best practice when unit testing a controller? Choose 2 answers
A. Simulate user interaction by leveraging Test.setMock().
B. Verify correct page references by using getURLU
C. Access test data by using seeAllData=true.
D. Set query parameters by using getParameters().put	B,D
What Visualforce tag can be used to display custom messages in pages using the Salesforce UI styling for errors, warnings, and other types of messages?
A. <apex: customMessage>
B. <apex:error>
C. <apex:message>
D. <apex:pageMessage>	D
A developer has created a Team Member sObject that has a Master-Detail relationship to a Project sObject and a Lookup relationship to the User sObject. The developer must ensure that a User listed on a Team Member record has Read-Write access to the parent Project record.
How can the developer accomplish this if the Project sObject has a Private sharing model and thousands of Project records?
A. Create a Controller that uses the Without Sharing keyword.
B. Create a Criteria-Based Sharing Rule on the Project sObject.
C. Create a Team Member Trigger that inserts Project_Share records.
D. Create a Project Sharing Rule that shares to the Team Member Group	C
Given the following code, what value Will be output in the logs by line #8?
1 Contact con = new Contact( LastName = 'Smith', Department = 'Admin')
2 insert con;
3 Contact insertedContact=[select Name from Contact where id=con.Id];
4 Savepoint sp_admin = Database.setSavepoint();
5 con.Department = 'HR'; D}
6 update con;
7 Database.rollback(sp_admin);
8 console.log(Limits.getDmlStatements());
A. 5
B. 3
C. 4
D. 2	C
What is a recommended practice with regard to the Apex CPU limit? Choose 2 answers
A. Optimize SOQL query performance.
B. Use Map collections to cache sObjects.
C. Avoid nested Apex iterations.
D. Reduce view state in Visualforce pages.	B,C
A developer wants to create a Visualforce page that allows a user to search for a given account by Name.
If the account is found, the account details should be populated on screen. If no account is found, an error message should be displayed to the user.
How can this be accomplished? Choose 2 answers
A. Use the (apex: information) tag to display the error message.
B. Use the ApexPages.addMessage() method to add the error message.
C. Use the <apex:pageMessages> tag to display the error message.
D. Use the account.addError( ) method to add the error message.	B,C
A developer has built a multi-page wizard using a single Custom Controller to query and update data.
Users are complaining that the pages are loading slowly.
What will improve performance? Choose 3 answers
A. Reducing the view state.
B. Using actionRegion and rerender.
C. Turning off the standard stylesheet.
D. Setting the Apex Page attribute cache=true.
E. Using selective queries.	A,D,E
A developer writes the following Apex trigger so that when a Case is closed, a single Survey record is created for that Case.
The issue is that multiple Survey-c records are being created per Case.
trigger CaseTrigger on Case (after insert, after update)
List<Survey__c> createSurveys = new List<Survey__c>();
for (Case c : trigger.new)
if (c.IsClosed && (trigger.isInsert ll
trigger.isUpdate && trigger.oldMap.get(c.Id).IsClosed == false)){
createSurveys.add(new Survey__c(Case__c = c.Id));
insert createSurveys;
What could be the cause of this issue?
A. A user is creating the record as Closed.
B. A workflow rule is firing with a Create Task action.
C. A workflow rule is firing with a Field Update action.
D. A user is editing the record multiple times.	C
What is a potential design issue with the following code?
trigger accountTrigger on Account (before update){
Boolean processOpportunity = false;
List<opportunity> opptysClosedLost = new List<opportunity>()
List<opportunity> lstAllOpp = [select StageName
from Opportunity where accountId IN :Trigger.newMap.keySet()];
if(!lstAllOpp.isEmpty())
processOpportunity = true;
while(processOpportunity){
for(opportunity o : lstAllOpp)
if(o.StageName == 'Closed - Lost')
opptysClosedLost.add(o);
processOpportunity = false;
if(!opptysClosedLost.isEmpty())
delete opptysClosedLost; (could not find any error , was able to execute successfully , can you check the question once) There is a possibility of D being the answer if no error in the question.
A. SOQL could be avoided by creating a formula field for StageName in Account from the related Opportunity.
B. The code Will result in a System.LimitException : Too many script statements error.
C. The code will result in a System.DmlException:Entity_is_Deleted error.
D. The code will result in a System.LimitException: Apex CPU time limit exceeded error.	D
The Contact object has a custom field called "Zone." Its data type is "Text" and field length is 3.
What is the outcome after executing the following code snippet in the org?
List<Contact> contactsToBeInserted=new List<Contact>();
Contact contactInstance= new Contact(LastName='Smith', Department='Tech', Zone__c='IAD');
contactsToBeInserted.add(contactlnstance);
contactInstance= new Contact(LastName='Sm1th', Department='Tech', Zone__c='PITT');
contactsToBeInserted.add(contactlnstance);
Database.insert(contactsToBeInserted,true);
A. Both inserts succeed and the contact record that has the Zone value of 'PI'I'I"" is set to NULL.
B. A partial insert succeeds and the contact record that has the Zone value 'IAD' is inserted.
C. Both inserts succeed and the contact record that has the Zone value of 'PITT"" is truncated.
D. An unhandled DML exception is thrown and no contact records are inserted.	D
Which statement is true regarding the use of user input as part of a dynamic SOQL query?
A. Free text input should not be allowed, to avoid SOQL injection.
B. The String.format () method should be used to prevent injection.
C. Quotes should be escaped to protect against SOQL injection.
D. The string should be URL encoded by the input form to prevent errors.	C
A developer has written the following method:
static void processList(List<sobject> input){
Which code block can be used to call the method?
A. ProcessList (acc)
B. ProcessList ( [FIND 'Acme" ' RETURNING Account]
C. ProcessList([SELECT Id, Name FROM sObject WHERE Type = 'Account'])
D. For Account acc : [SELECT Id, Name FROM Account]	C
A developer encounters an error that states that the Apex heap size is exceeded.
Which technique may reduce heap size?
A. Add the transient keyword to the variable definition.
B. Move the variable definition inside the scope of the function.
C. Use static variables instead of instance variables.
D. Use SOQL for loops instead of standard SOQL queries.	D
A developer has a Debug method within a class, which is invoked hundreds of times.
What is the optimal functionality in the Developer Console to count the number of calls made to the method?
A. The "Execution Log" Panel.
B. The "Execution Stack" Panel.
C. The "Executed Units" tab under the Execution Overview Panel.
D. The "Execution Tree" tab under the Stack Tree Panel.	C
What is a consideration when testing batch Apex? Choose 2 answers
A. Test methods must execute the batch with a scope size of less than 200 records.
B. Test methods must call the batch execute() method once.
C. Test methods must use the @isTest (SeeAllData=true) annotation.
D. Test methods must run the batch between Test. startTest() and Test.stopTest	B,D
A developer is working on code that requires a call to an external web service from a batch.
How should the developer enable this functionality? [ Not sure ]
A. Implement a custom System.CalloutException class.
B. Include Database.AllowCallout() in the class definition.
C. Implement an @future method for the callout, and invoke it from the batch.
D. Specify ""callout=true"" in the batch implementation.	B
Which is a valid Apex REST Annotation? Choose 2 answers
A @HttpPatch
B. @HttpDelete
C. @HttpUpsert
D. @HttpAction	A,B
A customer requires that when the billing address field on an Account gets updated, the address field on all its related contact records should reflect the same update.
How can this requirement be met with minimal customizations?
A. Create an After Trigger on Account to update its related contact records on update.
B. Create a Workflow Rule on Account to update related child Contact records.
C. Create a Lightning Process on Account to update related child Contact records.
D. Create a scheduled batch job that updates all contact address fields based on the related Account record.	C
A company requires an external system to be notified whenever an account is updated.
What LimitException could the following code trigger? [ Not sure ]
trigger AccountTrigger on Account (after update)
for (Account updatedAccount : Trigger.new)
AccountTriggerHelper.notifyxternalSystem(updatedAccount.id);
public class AccountTriggerHelper
future(callout=true)
public static void notifyxternalSystemlId accountId)
Account acc = [Select id, name from.Account where accountId = :accountId];
Instantiate a new http object
Http h = new Http();
HttpRequest req = new HttpRequest();
req.setEndpoint('http://example.org/restService');
req.setMethod('POST');
req.setBody(JSON.serialize(acc));
HttpResponse res = h.send(req);
A. System.LimitException: Too many future calls
B. System.LimitException: Too many callouts
C. System.LimitException: Too many SOQL queries
D. System.CalloutException: Callout from tn'ggers are currently not supported	A
A developer is using a third-party JavaScript library to create a custom user interface in Visualforce.
The developer needs to use JavaScript to get data from a controller method in response to a user action.
How can the developer accomplish this?
A. Use <apex: actionFunction> to create a JavaScript wrapper for the controller method.
B. Use the @RemoteAction annotation on the method definition with JavaScript Remoting.
C. Use the SController global variable to access the controller method via JavaScript.
D. Use (apex: actionSupport> to enable JavaScript support for the controller method.	B
What is a consideration when using bind variables with dynamic SOQL? Choose 2 answers
A. Dynamic SOQL cannot reference fields on bind variables.
B. Dynamic SOQL cannot use bind variables.
C. Bind variables must be public or global.
D. Bind variables must be in local scope.	A,D
A developer created a custom component to display an HTML table. The developer wants to be able to use the component on different Visualforce Pages and specify different header text for the table.
Which tag should the developer use inside the component?
A. < apex:variable>
B. < apex:define>
C. <apex:param>
D. <apex:attribute>	D
How can the DISTANCE and GEOLOCATION functions be used in SOQL queries? Choose 2 answers
A. To filter results based on distance from a latitude and longitude.
B. To get the distance results from a latitude and longitude.
C. To order results by distance from a latitude or longitude.
D. To group results in distance ranges from a latitude and longitude"	A,C
When developing a Visualforce page that will be used by a global organization that does business in many languages and many currencies, which feature should be used?
Choose 3 answers
A. Custom Labels
B. convertCurrency()
C. Global Labels
D. Translation Workbench
E. getLocalCurrency()	A,B,D
What is a valid return type for the following SOSL query?
[FIND 'map""' IN ALL FIELDS RETURNING Account (Id, Name) , Contact, Opportunity, Lead]
A. List<sobject>
B. List<List<sObj ect>>
C. List<AggregateResult>
D. List<Account>	B
What level can a hierarchy custom setting be defined for? Choose 3 answers
A. Users
B. Groups
C. Profiles
D. Roles
E. Organization	A,C,E
Which API can be used to execute unit tests? Choose 3 answers
A. Streaming API
B. Test API
c. Tooling API
D. SOAP API
E. Metadata API	C,D,E
Which statement is true about using ConnectApi namespace (also called Chatter in Apex)? Choose 2 answers
A. Chatter in Apex methods honor the 'with sharing' and 'without sharing' keywords.
B. Chatter in Apex operations are synchronous, and they occur immediately.
C. Chatter in Apex methods do not run in system mode; they run in the context of the current user.
D. Many test methods related to Chatter in Apex require the IsTest (SeeAllData=true) annotation.	C,D
A developer receives a LimitException: Too many query rows: 50001 error when running code.
What debugging approach using the Developer Console provides the fastest and most accurate mechanism to identify a specific component that may be returning an unexpected number of rows?***
A. Count the number of Row Limit warning messages in the Debug Logs.
B. Add System.debug (System.getoueryRows () to the code to track SOQL usage.
C. Filter the Debug Log on SOQL_EXECUTE_END statements to track the results of each SOQL Query.
D. Use the Execution Overview to see the number of rows returned by each Executed Unit.	C
A developer is writing a Visualforce page to display a list of all of the checkbox fields found on a custom object.
What is the recommended mechanism the developer should use to accomplish this?
A. Schema class
B. Apex API
C. Schema Builder
D. Metadata API"	A
A developer is building a Visualforce page that interacts with external services.
Which interface should the developer implement to test this functionality? Choose 2 answers
A. HTTPCalloutMock
B. HTTPRequestMock
C. HTTPResponseMock
D. StaticResourceCalloutMock	A,D
A developer is writing unit tests for the following method
public static Boolean isFreezing(String celsiusTemp)
if(String.isNotBlank(celsiusTemp) && celsiusTemp.isNumeric())
return Decimal.valueof(celsiusTemp) <= 0;
return null;
Which assertion would be used in a negative test case?
A. System.assertEquals(true, isFreezing(null));
B. System. assertEquals (true, isFreezing( ' 0');
C System.assertEquals(null, isFreezing('asdf'));
D. System.assertEquals(true, isFreezing('lOO'));	C
During the order of execution of a Visualforce page GET request, what happens after this step: Evaluate constructors on controllers and extensions?
A. Evaluate constructors and expressions on custom components.
B. Create view state if < apex: form> exists.
C. Send the HTML response to the browser.
D. Evaluate expressions, action attributes, and method calls."	A
A developer has generated Apex code from a WSDL for an external web service. The web service requires Basic authentication.
What code should the developer use to authenticate?
A. Http.setHeader ( 'Authorization' , 'Basic QthZGprjpchVuIHNchFtZQ==');
B. stub.inputhth-Ieader3_x.put ( 'Authorization' , 'Basic QthZGprjpchVuIHIQchE'tZQ:')
C. Http.setAuthentication( 'Basic QthZGprjpchVuIHNchFtZQ:')
D. stub.authentication.put ( 'Authorization' , 'Basic QthZGprjpchVuIHNchFtZQ=='	B
What is the correct syntax for calling a controller action from a Visualforce page and updating part of the page once the action is completed? Choose 2 answers
A. <apex:commandFunction action=""{ !Save}"" value=""Save"" rendered=""thePageBlock""/>
B. <apex:actionFunction action=""{ !Save}"" name=""Save"" rerender=""thePageBlock""/>
C. <apex:commandButton action=""{ !Save}"" value=""Save"" redraw=""thePageBlock""/>
D. <apex:actionSupport action=""{ !Save} "" event=""onchange"" rerender=""thePageBlock""/>	B,D
Employee-c is a Child object of Company-c. The Company-c object has an external Id field Company_Id_c. How can a developer insert an Employee-c record linked to Company-c with a Company_Id_c of '999'?
a) Employee-c emp = new Employee-C(Name='Developer');
emp.Company_r = ' 999'
insert emp;
b ) Employee-c emp = new Employee-C(Name='Developer');
emp.Company_c = ' 999'
insert emp;
c) Employee-c emp = new Employee-C(Name='Developer');
emp. Company-c = new Company-c (Company_Id_c=' 999
insert emp;
d. Employee-c emp = new Employee-C(Name='Developer');
emp.Company_r = new Company-r (Company_Id_c=' 999
insert emp;	D
A developer has written an Apex trigger on Account. A workflow rule and field update cause the trigger to repeatedly update the Account records. How should the developer handle the recursive trigger?

A. Deactivate the trigger and move the logic into a Process or Flow.
B. Deactivate the workflow rule to prevent the field update from executing.
C. Use a static variable to prevent the trigger from executing more than once.
D. Use a global variable to prevent the trigger from executing more than once.	C
A developer encounters an error that states that Apex heap size is exceeded. Which technique may reduce the heap size?

A. Add the transient keyword to the variable definition.
B. Move the variable definition inside the scope of the function
C. Use static variables instead of instance variables.
D. Use SOQL for loops instead of standard SOQL queries.	D
Which of the following elements can be members of a public group? Choose 3

A. Territories
B. Case Teams
C. Users
D. Role
E. Profiles	A,C,D
A company requires all internal users to submit a Case for adding a new Account in Salesforce. The case record captures all the data required to create an Account. The case approval process is a manual process. When a case is approved, an Account record should automatically be created based on the case details. What is the recommended solution? 
A. Configure a custom button on the Case page to update the Case Status and insert a new Account record.
B. Develop an After Update trigger on Case to create an Account record based on Case Status. 
C. Develop a Before Update trigger on Case to create an Account record based on Case status.
D. Develop a Lightning Process to create an Account Record when the Case status becomes Approved.	D
A developer wants to retrieve and deploy metadata, perform simple CSV export of query results, and debug Apex REST calls by viewing JSON responses. Which tool should the developer use? 
A. Developer Console
B. Force.com Migration Tool 
C. Workbench 
D. Force.com IDE	C
What is the output of the following code snippet? 
1 Contact con = new Contact( LastName = <br>'JOHNSON', LeadSource = 'Web')
 2 3 Savepoint sp = Database.setSavepoint(); 
4 insert con; 
5 Database.rollback(sp); 
6 7 con.LeadSource = 'Email' 
8 insert con; 
A. A runtime error wil be thrown on line 5. 
B. The contact record will be inserted with Leadsource value Web. C. A runtime error wil be thrown on line 8. 
D. The contact record will be inserted with Leadsource value Email.	C
Which use case is an appropriate fit for the @future asynchronous Apex method? Choose 2 answers 
A. A developer has jobs that need larger query results than regular transactions allow.
B. A developer needs to segregate DML operations and bypass the mixed save DML error. 
C. A developer has long-running jobs with large data volumes that need to be performed in batches
D. A developer has long-running methods and needs to prevent delaying an Apex transaction.	B,D
A developer created a custom component to display an HTML table. The developer wants to be <br>able to use the component on different Visualforce Pages and specify different header text for <br>the table. Which tag should the developer use inside the component? 
A. <apex:variable>
B. <apex:define>
C. <apex:param><meta charset="utf-8" /><apex:param>
D. <apex:attribute>	D
Which of the following standard fields are indexed? Choose three answers
A. Name
B. CreatedBy
C. SystemModStamp
D. LastModifedDate
E. RecordType	A,C,E
A company wants to create a dynamic survey that navigates users through a different series of questions based on their previous responses. What is the recommended solution to meet this requirement? 
A. Dynamic Record Choice 
B. Lightning Process Builder
C. Visualforce and Apex 
D. Custom Lightning application	C
A developer has a Debug method within a class, which is invoked hundreds of times. What is the optimal functionality in the Developer Console to count the number of calls made to the method? 
A. The Execution Log Panel. 
B. The Execution Stack Panel.
C. The Executed Units tab under the Execution Overview Panel. 
D. The Execution Tree tab under the Stack Tree Panel.	C
A developer writes the fol owing code: public with sharing class OrderController { public
PaqeReference sendOrder() { Order__c order = new Order__c insert order; ExternalOrder
externalOrder = new ExternalOrder (order); Http h = new Http(); HttpRequest req = new
HttpRequest(); req.setEndpoint('https://www.example.org/v1/orders'); req.setMethod('POST');
req.setBody(JSON.serialize(externalOrder)); HttpResponse res = h.send(req); order =
(ExternalOrder)JSON.deserialize(res.getBody(),ExternalOrder.class); } } While testing the code,
the developer receives the following error message: System.CalloutException : You have
uncommitted work pending What should the developer do? Choose 2 answers
A. Use the asyncSend() method of the HTTP class to send the request in async context.
B. Ensure all callouts are completed prior to executing DML statements.
C. Move the web service callout into an @future method.
D. Use Database.insert (order, true) to immediately commit any database changes.	B,C
What is the correct syntax for calling a controller action from a Visualforce page and updating
part of the page once the action is completed? Choose 2 answers
A. < apex: commandFunction action="{ !Save}" value="Save" rendered="thePageBlock"/>
B. < apex:actionFunction action="{ !Save}" name="Save" rerender="thePageBlock"/>
C. < apex:commandButton action="{ !Save}" value="Save" redraw="thePageBlock"/>
D. < apex:actionSupport action="{ !Save} " event="" rerender="thePageBlock"/>	B,D
A developer needs to design a custom object that will be integrated into a back-end system.
What should the developer do to ensure good data quality and to ensure that data imports,
integrations, and searches perform well? Choose 2 answers
A. Configure a custom field as unique.
B. Configure a custom field as indexed.
C. Configure a custom field as external ID.
D. Configure a custom field as Salesforce ID.	A,C
When developing a Visualforce page that will be used by a global organization that does
business in many languages and many currencies, which feature should be used? Choose 3
answers
A. Custom Labels
B. ConvertCurrency()
C. Global Labels
D. Translation Workbench
E. GetLocalCurrency()	A,B,D
Which statement is true about Apex web service methods? Choose 3 answers
A. Web service methods can be exposed having a custom Apex class as parameter datatype.
B. Web service methods can be overloaded with methods of the same name in the same class.
C. Web service methods can only be added to Apex classes that are declared global.
D. Web service methods can only be added to Apex triggers that are declared global.
E. Web service methods cannot be deprecated in managed package code	A,C,E
A company requires an external system to be notified whenever an account is updated. What
LimitException could the following code trigger? trigger AccountTrigger on Account (after
update) { for (Account updatedAccount : Trigger.new) {
AccountTriggerHelper.notinyxternalSystem(updatedAccount.id); } } public class
AccountTriggerHelper { future(callout=true) public static void notinyxternalSystemlId accountId)
{ Account acc = [Select id, name from.Account where accountId = :accountId]; //Instantiate a
new http object Http h = new Http(); HttpRequest req = new HttpRequest(); req.setEndpoint('
http://example.org/restService'); req.setMethod('POST'); req.setBody(JSON.serialize(acc));
HttpResponse res = h.send(req); } }

A. System.LimitException: Too many future calls
B. System.LimitException: Too many callouts
C. System.LimitException: Too many SOQL queries
D. System.CalloutException: Callout from triggers are currently not supported	A
A developer has written a Visualforce page to create a new account with the following markup:
The Visualforce page has extra logic for validating the website field. How can the developer add
an error message next to the website field if the submitted value isn't valid?
A. Use Account . fields .website . addError (message)
B. Use throw new SObjectException(message).
C. Use Account . website . addError (message)
D. Use ApexPages . addMessage (message)	D
How can Apex be used with Visual Workflow?
A. To set the version of a Flow being run.
B. To start a Flow automaticaly.
C. To add custom styling to a Flow.
D. To control access to a Flow	B
The Contact object has a custom field called "Zone." Its data type is "Text" and field length is 3.
What is the outcome after executing the following code snippet in the org? List<Contact>
contactsToBeInserted=new List<Contact>(); Contact contactInstance= new
Contact(LastName='Smith', Department='Tech', Zone__c='IAD');
contactsToBeInserted.add(contactlnstance); contactInstance= new Contact(LastName='Sm1th',
Department='Tech', Zone__c='PITT'); contactsToBeInserted.add(contactlnstance);
Database.insert(contactsToBeInserted,true);
A. Both inserts succeed and the contact record that has the Zone value of 'PI`I'I" is set to NULL.
B. A partial insert succeeds and the contact record that has the Zone value 'IAD' is inserted.
C. Both inserts succeed and the contact record that has the Zone value of 'PITT" is truncated.
D. An unhandled DML exception is thrown and no contact records are inserted.	D
A Visualforce page controller calls an external web service to get a list of records and display
them on the page. The external web service has a complex backend and generally takes a long
time to return results, causing timeouts. What can be done to avoid timeouts and display the
results without any errors?
A. Use the setTimeout () method on the HttpRequest to increase the timeout of the callout.
B. Create a callback method and create an instance of a Continuation object in an action
method.
C. Implement the Batchable interface to perform the callout and capture the response in the
batch job.
D. Use the tag and keep pol ing to check the status of the response in the controller.	B
How could a developer create a Visualforce page for a Multilanguage organization? Choose 2
answers
A. Use by default to support translation workbench.
B. Use custom labels to display validation rule errors in the current user's language.
C. Use custom labels to display text in the current user's language.
D. Use the language attribute of to support translation workbench.	C,D
Choose the correct definition for <apex:message>
A. Standard Salesforce formatting, throws a specific message on a page
B. Standard Salesforce formatting, shows all errors that occur on page. Can add more
messages through the "ApexPages.addMessage" function
C. A single message, without formatting, that can be associated with a specific component on
the page
D. No formatting; displays all errors on a pag	C
A developer is creating unit tests for code that makes SOAP web service callouts. The
developer needs to insert some test data as a part of the unit tests setup. What are three
actions to enable this functionality?
A. Surround the callout with Test.startTest(), Test.stopTest().
B. Surround the data insertion with Test.startTest(), Test.stopTest().
C. Implement the WebServiceMock interface.
D. Update code to call Test.setMock().
E. Implement the HttpCal outMock interface.	C,D
developer wrote a Visualforce page for Sales Reps to add products to an order. The page
takes a URL query parameter, productFamily, which filters the product results. The test method
for the filter behavior has an assertion failing due to an incorrect number of results. Why could
the test be failing? Choose 2 answers
A. The test does not call Test.startTest()
B. The test does not create product data.
C. The test is not run by a System Administrator.
D. The test does not set the current page reference.	B,D
Given the fol owing code sample, what is a potential issue regarding bulk processing of
records? trigger accountTestTrggr on Account (before insert, before update) Account acct =
Trigger.new[0]; List <Contact> contacts = new List <Contact> ([select id, salutation, firstname,
lastname,email from Contact where accountId
= :acct.Id]); for (Contact con: contacts) con.Title = 'Not Selected'; update contacts;
A. The code wil not execute because the record in the list can be nul and cause an exception.
B. The code wil process one record that is called explicitly per execution.
C. The code wil not execute because the list can be nul and cause an exception.
D. The code wil have to be invoked multiple times to process all the records.	B
Choose the correct definition for <apex:pageMessage>
A. Standard Salesforce formatting, throws a specific message on a page
B. Standard Salesforce formatting, shows all errors that occur on page. Can add more
messages through the "ApexPages.addMessage" function
C. A single message, without formatting, that can be associated with a specific component on
the page
D. No formatting; displays all errors on a page	A
What is the correct order of execution for Visualforce Page "get" requests (initial page visit)
A. 1: Evaluate constructors on controller and extensions
2: If there's a element, create the view state
3: Evaluate expressions, attribute actions, and other method calls (getters/setters) on main page
4: Evaluate constructors, extensions, and expression on attribute definitions on any custom
components present
5: Send HTML to Browser
B. 1: Evaluate constructors on controller and extensions
2: Evaluate constructors, extensions, and expression on attribute definitions on any custom
components present
3: Evaluate expressions, attribute actions, and other method calls (getters/setters) on main page
4: If there's a element, create the view state
5: Send HTML to Browser
C. 1: Evaluate constructors, extensions, and expression on attribute definitions on any custom
components present
2: Evaluate constructors on controller and extensions
3: Evaluate expressions, attribute actions, and other method calls (getters/setters) on main page
4: If there's a element, create the view state
5: Send HTML to Browser	B
A developer has built a multi-page wizard using a single Custom Controller to query and update
data. Users are complaining that the pages are loading slowly. What wil improve performance?
Choose 3 answers
A. Reducing the view state.
B. Using actionRegion and rerender.
C. Turning off the standard stylesheet.
D. Setting the Apex Page attribute cache=true.
E. Using selective queries.	A,D,E
Choose the correct definition for <apex:pageMessages>
A. Standard Salesforce formatting, throws a specific message on a page
B. Standard Salesforce formatting, shows all errors that occur on page. Can add more
messages through the "ApexPages.addMessage" function
C. A single message, without formatting, that can be associated with a specific component on
the page
D. No formatting; displays all errors on a page	B
Which statement is true about using ConnectApi namespace (also called Chatter in Apex)?
Choose 2 answers
A. Chatter in Apex methods honor the 'with sharing' and 'without sharing' keywords.
B. Chatter in Apex operations are synchronous, and they occur immediately.
C. Chatter in Apex methods do not run in system mode; they run in the context of the current
user.
D. Many test methods related to Chatter in Apex require the BIsTest (SeeAl Data=true)
annotation	C,D
A developer wants to create a Visualforce page that allows a user to search for a given account by Name. If the account is found, the account details should be populated on screen. If no
account is found, an error message should be displayed to the user. How can this be
accomplished? Choose 2 answers
A. Use the (apex: information) tag to display the error message.
B. Use the ApexPages.addMessage () method to add the error message.
C. Use the < apex:pageMessages > tag to display the error message.
D. Use the account.addError( ) method to add the error message.	B,C
The "action" attribute on <apex:page> is ONLY evaluated on which type of request?
A. Get request
B. Postback request	A
A customer requires that when the bil ing address field on an Account gets updated, the address
field on all its related contact records should reflect the same update. How can this requirement
be met with minimal customizations?
A. Create an After Trigger on Account to update its related contact records on update.
B. Create a Workflow Rule on Account to update related child Contact records.
C. Create a Lightning Process on Account to update related child Contact records.
D. Create a scheduled batch job that updates all contact address fields based on the related
Account record.	C
What is a valid request for the following REST method: @HttpPost global static void
myPostMethod(String sl,Integer il, Boolean bl, String b2)
Choose 2 answers
A. < request> < sl>my first string < 11>123 < 32>my second string < b1>false < /request>
B. < request> < sl>"my first string" < il>123 < sZ>"my second string" < bl>false < /request>
C. Sl" : "my first string", 11" : "123", "b1" : "false", "S2" : "my second string"
D. "il" : 123, "S1" : "my first string", "S2" : "my second string", "bl" : false	B,D
A developer has created a solution using the SOAP API for authenticating Communities users.
What is needed when issuing the login()Call? Choose 2 answers
A. Organization Id
B. Session Id
C. Username and Password
D. Security Token	C,D
What is a controller value that wil NOT be saved in the viewstate of a Visualforce page?
Choose 3 answers
A. A variable declared with the Transient keyword.
B. A variable of a type that is a collection of SObjects.
C. A system-generated object such as a Schema Describe object.
D. A variable declared with the Static keyword.
E. A variable of a type that is a custom Apex class.	A,C,D
What is a potential design issue with the following code? trigger accountTrigger on Account(before update) { Boolean processOpportunity = false; List<opportunity> opptysClosedLost =new List<opportunity>(); List<opportunity> lstAl Opp = [select StageName from Opportunitywhere accountId IN :Trigger.newMap.keySet()]; if(!lstAl Opp.isEmpty()) processOpportunity =true; while(processOpportunity) { for(opportunity o : lstAl Opp) { if(o.StageName == 'Closed
Lost') opptysClosedLost.add(o); processOpportunity = false; } } if(!opptysClosedLost.isEmpty()
delete opptysClosedLost;
A. SOQL could be avoided by creating a formula field for StageName in Account from the
related Opportunity.
B. The code Wil result in a System.LimitException : Too many script statements error.
C. The code wil result in a System.DmlException:Entity_is_Deleted error.
D. The code wil result in a System.LimitException: Apex CPU time limit exceeded error.	D
A developer has a page with two extensions overriding the Standard controller for Case.
<apex:page standardController="Case" extension3="CaseExtensionOne,CaseExtension Two"
showHeader="false"> Each extension has a method called Save. The page has a command
button as defined: <apex:commandButton value="Save" action="{!save}"/> What wil happen
when a user clicks the command button?
A. Al of the three Save methods wil be executed.
B. Save from Case Standard Controller wil be executed.
C. Save from CaseExtensionTwo wil be executed.
D. Save from CaseExtensionOne wil be executed.	D
In which of the following scenarios would it be acceptable to use programmatic sharing instead
of declarative sharing?
A. Every record created by sales users needs to be visible to their respective manager
B. Poor performance when using native sharing components
C. Team functionality is required on custom objects
D. Here is an existing, external system of truth for user access assignments which wil continue
to drive access and be integrated with salesforce
E. You need to change record access to read/write for all users utilising a lightning component	B,C,D
A developer is writing a Visualforce page to display a list of all of the checkbox fields found on a
custom object. What is the recommended mechanism the developer should use to accomplish
this?
A. Schema class
B. Apex API
C. Schema Builder
D. Metadata API	A
A developer has generated Apex code from a WSDL for an external web service. The web
service requires Basic authentication. What code should the developer use to authenticate?
A. Http. setHeader ( 'Authorization' , 'Basic QthZGprjpchVuIHNchFtZQ==');
B. Stub . inputhth-Ieader3_x.put ('Authorization' , 'Basic QthZGprjpchVuIHIQchE`tZQ:'
C. Http. setAuthentication( 'Basic QthZGprjpchVuIHNchFtZQ:'
D. Stub.authentication.put ( 'Authorization' , 'Basic QthZGprjpchVuIHNchFtZQ=='	B
What is the optimal syntax for adding a link to a case in a Visualforce page? Choose 2 answers
A. < apex:outputLink value="{!URLFOR($Action.Case.Open, case)}" target="_blank"> []
{lcase.Name} < /apex:outputLink>
B. < apex:outputLink value="/{!case.Id}" target="_blank"> [] {lcase.Name} < /apex:outputLink>
C. < apex:outputLink value="{!URLFOR($Action.Case.View,case.Id)}" target="_blank"> (LIE
{!case.Name} < /apex:outputLink>
D. < apex:outputLink value="{!viewCase(case.Id)}" target="_blank"> [] {lcase.Name} <
/apex:outputLink>	B,C