### **Salesforce Certified Platform Developer I** 

---
QUESTION 1 
What are two uses for External IDs? (Choose two.) 

A. To create relationships between records imported from an external system. 
B. To create a record in a development environment with the same Salesforce ID as in another environment 
C. To identify the sObject type in Salesforce 
D. To prevent an import from creating duplicate records using Upsert 

Answer: A D 

---
QUESTION 2 
In a single record, a user selects multiple values from a multi-select picklist. 
How are the selected values represented in Apex? 

A. As a List<String> with each value as an element in the list 
B. As a String with each value separated by a comma 
C. As a String with each value separated by a semicolon 
D. As a Set<String> with each value as an element in the set 

Answer: C 

---
QUESTION 3 Given: 
Map<ID, Account> accountMap = new Map>ID, Account> ([SELECT Id, Name FROM Account]); What are three valid 
Apex loop structures for iterating through items in the collection? (Choose three.) 

A. for (ID accountID : accountMap.keySet()) {…} 
B. for (Account accountRecord : accountMap.values()) {…} 
C. for (Integer i=0; I < accountMap.size(); i++) {…} 
D. for (ID accountID : accountMap) {…} 
E. for (Account accountRecord : accountMap.keySet()) {…} 

Answer: A B C 

---
QUESTION 4 
For which three items can a trace flag be configured? (Choose three.) 

A. Apex Trigger 
B. Apex Class 
C. Process Builder 
D. User 
E. Visualforce 

Answer: A B D 

---
QUESTION 5 
Which set of roll-up types are available when creating a roll-up summary field? 

A. COUNT, SUM, MIN, MAX 
B. AVERAGE, SUM, MIN, MAX 
C. SUM, MIN, MAX 
D. AVRAGE, COUNT, SUM, MIN, MAX 

Answer: A 

---
QUESTION 6 
Using the Schema Builder, a developer tries to change the API name of a field that is referenced in an Apex test class. 
What is the end result? 

A. The API name is not changed and there are no other impacts. 
B. The API name of the field and the reference in the test class is changed. 
C. The API name of the field is changed, and a warning is issued to update the class. 
D. The API name of the field and the reference in the test class is updated. 

Answer:  ~~C~~ D

---
QUESTION 7 
Which approach should be used to provide test data for a test class? 

A. Query for existing records in the database. 
B. Execute anonymous code blocks that create data. 
C. Use a test data factory class to create test data. 
D. Access data in @TestVisible class variables. 

Answer: C 

---
QUESTION 8 
When an Account’s custom picklist field called Customer Sentiment is changed to a value of “Confused”, a new related 
Case should automatically be created. 
Which two methods should a developer use to create this case? (Choose two.) 

A. Process Builder 
B. Apex Trigger 
C. Custom Button 
D. Workflow Rule 

Answer: A B 

---
QUESTION 9 
Which two strategies should a developer use to avoid hitting governor limits when developing in a multi-tenant 
environment? (Choose two.) 

A. Use collections to store all fields from a related object and not just minimally required fields. 
B. Use methods from the “Limits” class to monitor governor limits. 
C. Use SOQL for loops to iterate data retrieved from queries that return a high number of rows. 
D. Use variables within Apex classes to store large amounts of data. 

Answer: B C 

---
QUESTION 10 
When viewing a Quote, the sales representative wants to easily see how many discounted items are included in the Quote 
Line Items. 
What should a developer do to meet this requirement? 

A. Create a trigger on the Quote object that queries the Quantity field on discounted Quote Line Items. 
B. Create a Workflow Rule on the Quote Line Item object that updates a field on the parent Quote when the item is 
discounted. 
C. Create a roll-up summary field on the Quote object that performs a SUM on the quote Line Item Quantity field, 
filtered for only discounted Quote Line Items. 
D. Create a formula field on the Quote object that performs a SUM on the Quote Line Item Quantity field, filtered for 
only discounted Quote Line Items. 

Answer: C 

---
QUESTION 11 
A Platform Developer needs to write an Apex method that will only perform an action if a record is assigned to a specific 
Record Type. 
Which two options allow the developer to dynamically determine the ID of the required Record Type by its name? 
(Choose two.) 

A. Make an outbound web services call to the SOAP API. 
B. Hardcode the ID as a constant in an Apex class. 
C. Use the getRecordTypeInfosByName() method in the DescribeSObjectResult class. 
D. Execute a SOQL query on the RecordType object. 

Answer: C D 

---
QUESTION 12 
A Visualforce page is required for displaying and editing Case records that includes both standard and custom 
functionality defined in an Apex class called myControllerExtension. 
The Visualforce page should include which <apex:page> attribute(s) to correctly implement controller functionality? 

A. controller=“Case” and extensions=“myControllerExtension” 
B. extensions=“myControllerExtension” 
C. controller=“myControllerExtension” 
D. standardController=“Case” and extensions=“myControllerExtension” 

Answer: D 

---
QUESTION 13 
A developer needs to test an Invoicing system integration. After reviewing the number of transactions required for the 
test, the developer estimates that the test data will total about 2 GB of data storage. Production data is not required for the 
integration testing. 
Which two environments meet the requirements for testing? (Choose two.) 

A. Developer Sandbox 
B. Full Sandbox 
C. Developer Edition 
D. Partial Sandbox 
E. Developer Pro Sandbox 

Answer: B D 

---
QUESTION 14 
Which three declarative fields are correctly mapped to variable types in Apex? (Choose three.) 

A. Number maps to Decimal. 
B. Number maps to Integer. 
C. TextArea maps to List of type String. 
D. Date/Time maps to Dateline. 
E. Checkbox maps to Boolean. 

Answer: A D E 

---
QUESTION 15 
A developer needs to join data received from an integration with an external system with parent records in Salesforce. 
The data set does not contain the Salesforce IDs of the parent records, but it does have a foreign key attribute that can be 
used to identify the parent. 
Which action will allow the developer to relate records in the data model without knowing the Salesforce ID? 

A. Create and populate a custom field on the parent object marked as Unique. 
B. Create a custom field on the child object of type External Relationship. 
C. Create and populate a custom field on the parent object marked as an External ID. 
D. Create a custom field on the child object of type Foreign Key. 

Answer: D 

---
QUESTION 16 
A developer wants to override a button using Visualforce on an object. 
What is the requirement? 

A. The controller or extension must have a PageReference method. 
B. The standardController attribute must be set to the object. 
C. The action attribute must be set to a controller method. 
D. The object record must be instantiated in a controller or extension. 

Answer: B 

---
QUESTION 17 
The operation manager at a construction company uses a custom object called Machinery to manage the usage 
and maintenance of its cranes and other machinery. The manager wants to be able to assign machinery to different 
constructions jobs, and track the dates and costs associated with each job. More than one piece of machinery can be 
assigned to one construction job. 
What should a developer do to meet these requirements? 

A. Create a lookup field on the Construction Job object to the Machinery object. 
B. Create a lookup field on the Machinery object to the Construction Job object. 
C. Create a junction object with Master-Detail Relationship to both the Machinery object and the Construction Job object. 
D. Create a Master-Detail Lookup on the Machinery object to the Construction Job object. 

Answer: ~~A~~ C

---
QUESTION 18 
What should a developer use to implement an automatic Approval Process submission for Cases? 

A. An Assignment Rule 
B. Scheduled Apex 
C. Process Builder 
D. A Workflow Rule 

Answer: C 

---
QUESTION 19 
A developer writes the following code: 
What is the result of the debug statement? 

```java
List<Account> acc = [SELECT ID FROM ACCOUNT LIMIT 1];
Delete acc;
Database.emptyRecycleBin(acc);
System.Debug(Limits.getDMLStatements() + ',' + Limits.getLimitDMLStatements());
```

A. 1, 100 
B. 1, 150 
C. 2, 150 
D. 2, 200 

Answer: C 

---
QUESTION 20 
What is a benefit of using an after insert trigger over using a before insert trigger? 

A. An after insert trigger allows a developer to bypass validation rules when updating fields on the new record. 
B. An after insert trigger allows a developer to insert other objects that reference the new record. 
C. An after insert trigger allows a developer to make a callout to an external service. 
D. An after insert trigger allows a developer to modify fields in the new record without a query. 

Answer: B 

---
QUESTION 21 
A developer has the controller class below. 
Which code block will run successfully in an execute anonymous window? 

A. myFooController m = new myFooController();System.assert(m.prop !=null); 
B. myFooController m = new myFooController();System.assert(m.prop ==0); 
C. myFooController m = new myFooController();System.assert(m.prop ==null); 
D. myFooController m = new myFooController();System.assert(m.prop ==1); 

Answer: C 

---
QUESTION 22 
Where can a developer identify the time taken by each process in a transaction using Developer Console log 
inspector? 

A. Performance Tree tab under Stack Tree panel 
B. Execution Tree tab under Stack Tree panel 
C. Timeline tab under Execution Overview panel 
D. Save Order tab under Execution Overview panel 

Answer: C 

---
QUESTION 23 
Which statement results in an Apex compiler error? 

A. Map<Id,Leas> lmap = new Map<Id,Lead>([Select ID from Lead Limit 8]); 
B. Date d1 = Date.Today(), d2 = Date.ValueOf(‘2018-01-01’); 
C. Integer a=5, b=6, c, d = 7; 
D. List<string> s = List<string>{‘a’,‘b’,‘c’); 

Answer: D 

---
QUESTION 24 
What is a capability of the <ltng:require> tag that is used for loading external Javascript libraries in Lightning 
Component? (Choose three.) 

A. Loading files from Documents. 
B. One-time loading for duplicate scripts. 
C. Specifying loading order. 
D. Loading scripts in parallel. 
E. Loading externally hosted scripts. 

Answer: B C D 

---
QUESTION 25 
A lead object has a custom field Prior_Email__c. The following trigger is intended to copy the current Email into the 
Prior_Email__c field any time the Email field is changed: 
Which type of exception will this trigger cause? 

A. A null reference exception 
B. A compile time exception 
C. A DML exception 
D. A limit exception when doing a bulk update 

Answer: C 

---
QUESTION 26 
A developer executes the following query in Apex to retrieve a list of contacts for each account: List<account> accounts 
= [Select ID, Name, (Select ID, Name from Contacts) from Account] ; Which two exceptions may occur when it 
executes? (Choose two.) 

A. CPU limit exception due to the complexity of the query. 
B. SOQL query row limit exception due to the number of contacts. 
C. SOQL query limit exception due to the number of contacts. 
D. SOQL query row limit exception due to the number of accounts. 

Answer: C D 

---
QUESTION 27 
A developer is asked to set a picklist field to ‘Monitor’ on any new Leads owned by a subnet of Users. How should the 
developer implement this request? 

A. Create an after insert Lead trigger. 
B. Create a before insert Lead trigger. 
C. Create a Lead Workflow Rule Field Update. 
D. Create a Lead formula field. 

Answer: C 

---
QUESTION 28 
Which two statements are true about using the @testSetup annotation in an Apex test class? (Choose two.) 

A. The @testSetup annotation cannot be used when the @isTest(SeeAllData=True) annotation is used. 
B. Test data is inserted once for all test methods in a class. 
C. Records created in the @testSetup method cannot be updates in individual test methods. 
D. The @testSetup method is automatically executed before each test method in the test class is executed. 

Answer: D 

---
QUESTION 29 
A developer created a Visualforce page and a custom controller with methods to handle different buttons and events that 
can occur on the page. 
What should the developer do to deploy to production? 

A. Create a test class that provides coverage of the Visualforce page. 
B. Create a test page that provides coverage of the Visualforce page. 
C. Create a test page that provides coverage of the custom controller. 
D. Create a test class that provides coverage of the custom controller. 

Answer: D 

---
QUESTION 30 
What are two benefits of the Lightning Component framework? (Choose two.) 

A. It simplifies complexity when building pages, but not applications. 
B. It provides an event-driven architecture for better decoupling between components. 
C. It promotes faster development using out-of-box components that are suitable for desktop and mobile devices. 
D. It allows faster PDF generation with Lightning components. 

Answer: B C 

---
QUESTION 31 
Universal Containers wants Opportunities to be locked from editing when reaching the Closed/Won stage. Which two 
strategies should a developer use to accomplish this? (Choose two.) 

A. Use a Visual Workflow. 
B. Use a validation rule. 
C. Use the Process Automation Settings. 
D. Use a Trigger. 

Answer: B D 

---
QUESTION 32 
Which three options can be accomplished with formula fields? (Choose three.) 

A. Generate a link using the HYPERLINK function to a specific record. 
B. Display the previous value for a field using the PRIORVALUE function. 
C. Determine if a datetime field value has passed using the NOW function. 
D. Return and display a field value from another object using the VLOOKUP function. 
E. Determine which of three different images to display using the IF function. 

Answer: A C E 

---
QUESTION 33 
Which SOQL query successfully returns the Accounts grouped by name? 

A. SELECT Type, Max(CreatedDate) FROM Account GROUP BY Name 
B. SELECT Name, Max(CreatedDate) FROM Account GROUP BY Name 
C. SELECT Id, Type, Max(CreatedDate) FROM Account GROUP BY Name 
D. SELECT Type, Name, Max(CreatedDate) FROM Account GROUP BY Name LIMIT 5 

Answer: B 

---
QUESTION 34 
A method is passed a list of generic sObjects as a parameter. 
What should the developer do to determine which object type (Account, Lead, or Contact, for example) to cast each 
sObject? 

A. Use the first three characters of the sObject ID to determine the sObject type. 
B. Use the getSObjectType method on each generic sObject to retrieve the sObject token. 
C. Use the getSObjectName method on the sObject class to get the sObject name. 
D. Use a try-catch construct to cast the sObject into one of the three sObject types. 

Answer: B 

---
QUESTION 35 
Which two number expressions evaluate correctly? (Choose two.) 

A. Double d = 3.14159; 
B. Integer I = 3.14159; 
C. Decimal d = 3.14159; 
D. Long l = 3.14159; 

Answer: A C 

---
QUESTION 36 
How should a developer avoid hitting the governor limits in test methods? 

A. Use @TestVisible on methods that create records. 
B. Use Test.loadData() to load data from a static resource. 
C. Use @IsTest (SeeAllData=true) to use existing data. 
D. Use Test.startTest() to reset governor limits. 

Answer: D 

---
QUESTION 37 
What are two valid options for iterating through each Account in the collection List<Account> named AccountList? 
(Choose two.) 

A. for (Account theAccount : AccountList) {…} 
B. for(AccountList) {…} 
C. for (List L : AccountList) {…} 
D. for (Integer i=0; i < AccountList.Size(); i++) {…} 

Answer: A D 

---
QUESTION 38 
How should a developer create a new custom exception class? 

A. public class CustomException extends Exception{} 
B. CustomException ex = new (CustomException)Exception(); 
C. public class CustomException implements Exception{} 
D. (Exception)CustomException ex = new Exception(); 

Answer: A 

---
QUESTION 39 
A developer wrote a unit test to confirm that a custom exception works properly in a custom controller, but the test failed 
due to an exception being thrown. 
Which step should the developer take to resolve the issue and properly test the exception? 

A. Use try/catch within the unit test to catch the exception. 
B. Use the finally bloc within the unit test to populate the exception. 
C. Use the database methods with all or none set to FALSE. 
D. Use Test.isRunningTest() within the custom controller. 

Answer: A 

---
QUESTION 40 
Which two Apex data types can be used to reference a Salesforce record ID dynamically? (Choose two.) 

A. ENUM 
B. sObject 
C. External ID 
D. String 

Answer: A D 

---
QUESTION 41 
A developer encounters APEX heap limit errors in a trigger. 
Which two methods should the developer use to avoid this error? (Choose two.) 

A. Use the transient keyword when declaring variables. 
B. Query and store fields from the related object in a collection when updating related objects. 
C. Remove or set collections to null after use. 
D. Use SOQL for loops instead of assigning large queries results to a single collection and looping through the collection. 

Answer: A D 

---
QUESTION 42 
A developer is asked to create a PDF quote document formatted using the company’s branding guidelines, and 
automatically save it to the Opportunity record. 
Which two ways should a developer create this functionality? (Choose two.) 

A. Install an application from the AppExchange to generate documents. 
B. Create a Visualforce page with custom styling. 
C. Create an email template and use it in Process Builder. 
D. Create a visual flow that implements the company’s formatting. 

Answer: A B 

---
QUESTION 43 
How should a developer prevent a recursive trigger?

A. Use a “one trigger per object” pattern. 
B. Use a static Boolean variable. 
C. Use a trigger handler. 
D. Use a private Boolean variable. 

Answer: D 

---
QUESTION 44 
How can a developer set up a debug log on a specific user? 

A. It is not possible to setup debug logs for users other than yourself. 
B. Ask the user for access to their account credentials, log in as the user and debug the issue. 
C. Create Apex code that logs code actions into a custom object. 
D. Set up a trace flag for the user, and define a logging level and time period for the trace. 

Answer: D 

---
QUESTION 45 
What is the result of the debug statements in testMethod3 when you create test data using testSetup in below code? 

A. Account0.Phone=333-8781, Account1.Phone=333-8780 
B. Account0.Phone=888-1515, Account1.Phone=999-2525 
C. Account0.Phone=333-8780, Account1.Phone=333-8781 
D. Account0.Phone=888-1515, Account1.Phone=999-1515

Answer: C 

---
QUESTION 46 
A developer needs to display all of the available fields for an object. 
In which two ways can the developer retrieve the available fields if the variable myObject represents the name of the 
object? (Choose two.) 

A. Use myObject.sObjectType.getDescribe().fieldSet() to return a set of fields. 
B. Use mySObject.myObject.fields.getMap() to return a map of fields. 
C. Use Schema.describeSObjects(new String[]{myObject})[0].fields.getMap() to return a map of fields. 
D. Use getGlobalDescribe().get(myObject).getDescribe().fields.getMap() to return a map of fields. 

Answer: B C 

---
QUESTION 47 
An org has a single account named ‘NoContacts’ that has no related contacts. Given the query: 
List<Account> accounts = [Select ID, (Select ID, Name from Contacts) from Account where Name=‘NoContacts’]; 
What is the result of running this Apex? 

A. accounts[0].contacts is invalid Apex. 
B. accounts[0].contacts is an empty Apex. 
C. accounts[0].contacts is Null. 
D. A QueryException is thrown. 

Answer: B 

---
QUESTION 48 
A platform developer at Universal Containers needs to create a custom button for the Account object that, when clicked, 
will perform a series of calculations and redirect the user to a custom Visualforce page. 
Which three attributes need to be defined with values in the <apex:page> tag to accomplish this? (Choose three.) 

A. action 
B. renderAs 
C. standardController 
D. readOnly 
E. extensions 

Answer:  ~~A B C~~ A C E 

---
QUESTION 49 
Which tool allows a developer to send requests to the Salesforce REST APIs and view the responses? 

A. REST resource path URL 
B. Workbench REST Explorer 
C. Developer Console REST tab 
D. Force.com IDE REST Explorer tab 

Answer: B 

---
QUESTION 50 
Which three options allow a developer to use custom styling in a Visualforce page? (Choose three.) 

A. <apex:stylesheet> tag 
B. Inline CSS 
C. <apex:style>tag 
D. <apex:stylesheets>tag 
E. A static resource 

Answer: A B E 

---
QUESTION 51 
Which approach should a developer use to add pagination to a Visualforce page? 

A. A StandardController 
B. The Action attribute for a page 
C. The extensions attribute for a page 
D. A StandardSetController 

Answer: D 

---
QUESTION 52 
While writing a test class that covers an OpportunityLineItem trigger, a Developer is unable to create a standard 
PriceBook since one already exists in the org. 
How should the Developer overcome this problem? 

A. Use Test.getStandardPricebookId() to get the standard PriceBook ID. 
B. Use @IsTest(SeeAllData=true) and delete the existing standard PriceBook. 
C. Use Test.loadData() and a Static Resource to load a standard Pricebook. 
D. Use @TestVisible to allow the test method to see the standard PriceBook. 

Answer: A 

---
QUESTION 53 
Why would a developer consider using a custom controller over a controller extension? 

A. To increase the SOQL query governor limits. 
B. To implement all of the logic for a page and bypass default Salesforce functionality 
C. To leverage built-in functionality of a standard controller 
D. To enforce user sharing settings and permissions 

Answer: B 

---
QUESTION 54 
What is the requirement for a class to be used as a custom Visualforce controller? 

A. Any top-level Apex class that has a constructor that returns a PageReference 
B. Any top-level Apex class that extends a PageReference 
C. Any top-level Apex class that has a default, no-argument constructor 
D. Any top-level Apex class that implements the controller interface 

Answer: ~~D~~ C 

---
QUESTION 55 
A developer working on a time management application wants to make total hours for each timecard available to 
application users. A timecard entry has a Master-Detail relationship to a timecard. 
Which approach should the developer use to accomplish this declaratively? 

A. A Visualforce page that calculates the total number of hours for a timecard and displays it on the page 
B. A Roll-Up Summary field on the Timecard Object that calculates the total hours from timecard entries for that 
timecard 
C. A Process Builder process that updates a field on the timecard when a timecard entry is created 
D. An Apex trigger that uses an Aggregate Query to calculate the hours for a given timecard and stores it in a custom 
field 

Answer: B 

---
QUESTION 56 
A newly hired developer discovers that there are multiple triggers on the case object. What should the developer consider 
when working with triggers? 

A. Developers must dictate the order of trigger execution. 
B. Trigger execution order is based on creation date and time. 
C. Unit tests must specify the trigger being tested. 
D. Trigger execution order is not guaranteed for the same sObject. 

Answer: D 

---
QUESTION 57 
Which two platform features align to the Controller portion of MVC architecture? (Choose two.) 

A. Process Builder actions 
B. Workflow rules 
C. Standard objects 
D. Date fields 

Answer: A B 

---
QUESTION 58 
A developer created a Lightning component to display a short text summary for an object and wants to use it with 
multiple Apex classes. 
How should the developer design the Apex classes? 

A. Have each class define method getObject() that returns the sObject that is controlled by the Apex class. 
B. Extend each class from the same base class that has a method getTextSummary() that returns the summary. 
C. Have each class implement an interface that defines method getTextSummary() that returns the summary. 
D. Have each class define method getTextSummary() that returns the summary. 

Answer: C 

---
QUESTION 59 
A developer needs to create a Visualforce page that displays Case data. The page will be used by both support reps and 
support managers. The Support Rep profile does not allow visibility of the Customer_Satisfaction__c field, but the 
Support Manager profile does. 
How can the developer create the page to enforce Field Level Security and keep future maintenance to a minimum? 

A. Create one Visualforce Page for use by both profiles. 
B. Use a new Support Manager permission set. 
C. Create a separate Visualforce Page for each profile. 
D. Use a custom controller that has the with sharing keywords. 

Answer: D 

---
QUESTION 60 
Which approach should a developer take to automatically add a “Maintenance Plan” to each Opportunity that includes an 
“Annual Subscription” when an opportunity is closed? 

A. Build a OpportunityLineItem trigger that adds a PriceBookEntry record. 
B. Build an OpportunityLineItem trigger to add an OpportunityLineItem record. 
C. Build an Opportunity trigger that adds a PriceBookEntry record. 
D. Build an Opportunity trigger that adds an OpportunityLineItem record. 

Answer: D 

---
QUESTION 61 
When is an Apex Trigger required instead of a Process Builder Process? 

A. When a record needs to be created 
B. When multiple records related to the triggering record need to be updated 
C. When a post to Chatter needs to be created 
D. When an action needs to be taken on a delete or undelete, or before a DML operation is executed. 

Answer: D 

---
QUESTION 62 
Which three tools can deploy metadata to production? (Choose three.) 

A. Change Set from Developer Org 
B. Force.com IDE 
C. Data Loader 
D. Change Set from Sandbox 
E. Metadata API 

Answer: A D E 

---
QUESTION 63 
What are three characteristics of static methods? (Choose three.) 

A. Initialized only when a class is loaded 
B. A static variable outside of the scope of an Apex transaction 
C. Allowed only in outer classes 
D. Allowed only in inner classes 
E. Excluded from the view state for a Visualforce page 

Answer: A C E 

---
QUESTION 64 
How should a developer make sure that a child record on a custom object, with a lookup to the Account object, has the 
same sharing access as its associated account? 

A. Create a Sharing Rule comparing the custom object owner to the account owner. 
B. Create a validation rule on the custom object comparing the record owners on both records. 
C. Include the sharing related list on the custom object page layout. 
D. Ensure that the relationship between the objects is Master-Detail. 

Answer: D 

---
QUESTION 65 
What is the result when a Visualforce page calls an Apex controller, which calls another Apex class, which then results 
in hitting a governor limit? 

A. Any changes up to the error are saved. 
B. Any changes up to the error are rolled back. 
C. All changes before a savepoint are saved. 
D. All changes are saved in the first Apex class. 

Answer: B 

---
QUESTION 66 
When can a developer use a custom Visualforce page in a Force.com application? (Choose 2) 

A. To generate a PDF document with application data 
B. To create components for dashboards and layouts 
C. To deploy components between two organizations 
D. To modify the page layout settings for a custom object 

Answer: A B 

---
QUESTION 67 
A company has a custom object named Warehouse. Each Warehouse record has a distinct record owner, and is related to 
a parent Account in Salesforce.Which kind of relationship would a developer use to relate the Account to the Warehouse? 

A. One -to -Many 
B. Lookup 
C. Master -Detail 
D. Parent -Child 

Answer: B 

---
QUESTION 68 
Which type of code represents the Controller in MVC architecture on the Force.com platform? (Choose 2)

A. JavaScript that is used to make a menu item display itself. 
B. A static resource that contains CSS and images. 
C. Custom Apex and JavaScript coda that is used to manipulate data. 
D. StandardController system methods that are referenced by Visualforce. 

Answer: C D 

---
QUESTION 69 
Which resource can be included in a Lightning Component bundle?Choose 2 answers 

A. Apex class 
B. Adobe Flash 
C. JavaScript 
D. Documentation 

Answer: C D 

---
QUESTION 70 
What is an accurate constructor for a custom controller named "MyController"? 

A. public MyController () { account = new Account () ; } 
B. public MyController (sObject obj) { account = (Account) obj; } 
C. public MyController (List objects) { accounts = (List ) objects; } 
D. public MyController (ApexPages.StandardController stdController) { account = (Account) 
stdController.getRecord(); } 

Answer: A 

---
QUESTION 71 
A developer has a single custom controller class that works with a Visualforce Wizard to support creating and editing 
multiple sObjects. The wizard accepts data from user inputs across multiple Visualforce pages and from a parameter on 
the initial URLWhich statement is unnecessary inside the unit test for the custom 
controller? 

A. Public ExtendedController (ApexPages.StandardController cntrl) { } 
B. ApexPages.currentPage().getParameters().put('input', 'TestValue') 
C. Test.setCurrentPage(pageRef), 
D. String nextPage = controller.save().getUrl(); 

Answer: A D 

---
QUESTION 72 
What should a developer working in a sandbox use to exercise a new test Class before the developer deploys that test 
production?Choose 2 answers 

A. The REST API and ApexTestRun method 
B. The Apex Test Execution page in Salesforce Setup. 
C. The Test menu in the Developer Console. 
D. The Run Tests page in Salesforce Setup. 

Answer: B C 

---
QUESTION 73 
A user selects a value from a multi-select picklist. How is this selected value represented in Apex? 

A. As a string ending with a comma 
B. As a string 
C. As a list< String > with one element 
D. As a set< string > with one element 

Answer: B 

---
QUESTION 74 
A developer has a unit test that is failing. To identify the issue, the developer copies the code inside the test method and 
executes it via the Execute Anonymous Apex Tool. The code then executes without failing. Why did the unit test failed, 
but not the Execute Anonymous? 

A. The test method has a syntax error in the code. 
B. The test method relies on existing data in the database 
C. The test method use a try/catch block 
D. The test method calls an @future method. 

Answer: B 

---
QUESTION 75 
In which order does SalesForce execute events upon saving a record? 

A. Before Triggers; Validation Rules; After Triggers; Assignment Rules; Workflow Rules; Commit 
B. Validation Rules; Before Triggers; After Triggers; Workflow Rules; Assignment Rules; Commit 
C. Before Triggers; Validation Rules; After Triggers; Workflow Rules; Assignment Rules; Commit 
D. Validation Rules; Before Triggers; After Triggers; Assignment Rules; Workflow Rules; Commit 

Answer: A 

---
QUESTION 76 
What is a benefit of the Lightning Component framework?Choose 3 answers 

A. It uses client-side Apex controllers for logic. 
B. It uses a traditional publish-subscribe model. 
C. It uses an event-driven architecture 
D. It uses an MVC architectural design pattern. 
E. It uses server-side JavaScript controller for logic. 

Answer: B C D 

---
QUESTION 77 
A developer needs to provide a Visualforce page that lets users enter Product-specific details during a Sales cycle. How 
can this be accomplished? (Choose 2) 

A. Download a Managed Package from the AppExhange that provides a custom Visualforce page to modify. 
B. Copy the standard page and then make a new Visualforce page for Product data entry. 
C. Download an Unmanaged Package from the AppExchange that provides a custom Visualforce page to modify. 
D. Create a new Visualforce page and an Apex controller to provide Product data entry. 

Answer: C D 

---
QUESTION 78 
A developer creates a Workflow Rule declaratively that updates a field on an object. An Apex update trigger exists for 
that object. What happens when a user updates a record? 

A. No changes are made to the data. 
B. Both the Apex Trigger and Workflow Rule are fired only once. 
C. The Workflow Rule is fired more than once. 
D. The Apex Trigger is fired more than once. 

Answer: D 

---
QUESTION 79 
On a Visualforce page with a custom controller, how should a developer retrieve a record by using an ID that is passed 
on the URL? 

A. Use the constructor method for the controller. 
B. Use the $Action.View method in the Visualforce page. 
C. Create a new PageReference object with the Id. 
D. Use the tag in the Visualforce page. 

Answer: A 

---
QUESTION 80 
What is a capability of cross-object formula fields? Choose 3 answers 

A. Formula fields can reference fields from master-detail or lookup parent relationships. 
B. Formula fields can expose data the user does not have access to in a record. 
C. Formula fields can be used in three roll-up summaries per object. 
D. Formula fields can reference fields in a collect of records from a child relationship. 
E. Formula fields can reference fields from objects that are up to 10 relationships away. 

Answer: A B E 

---
QUESTION 81 
What actions types should be configured to display a custom success message? 

A. Update a record. 
B. Post a feed item. 
C. Delete a record. 
D. Close a case. 

Answer: A 

---
QUESTION 82 
A custom exception "RecordNotFoundException" is defined by the following code of block.public class 
RecordNotFoundException extends Exception()which statement can a developer use to throw a custom 
exception?choose 2 answers 

A. Throw new RecordNotFoundException("problem occured"); 
B. Throw new RecordNotFoundException(); 
C. throw RecordNotFoundException("problem occured"); 
D. Throw RecordNotFoundException(); 

Answer: A B 

---
QUESTION 83 
Which statement about change set deployments is accurate? (Choose 3) 

A. They use an all or none deployment model. 
B. They require a deployment connection. 
C. They ca be used to transfer Contact records. 
D. They can be used to deploy custom settings data. 
E. They can be used only between related organizations. 

Answer: A B E 

---
QUESTION 84 
What features are available when writing apex test classes?(Choose 2 Answers) 

A. The ability to select error types to ignore in the developer console. 
B. The ability to write assertions to test after a @future method. 
C. The ability to set and modify the CreatedDate field in apex tests. 
D. The ability to set breakpoints to freeze the execution at a given point. 
E. The ability to select testing data using csv files stored in the system. 

Answer: C E 

---
QUESTION 85 
Which actions can a developer perform using the Schema Builder?Choose 2 answers 

A. Create a custom field and automatically add it to an existing page layout. 
B. Create a view containing only standard and system objects. 
C. Create a custom object and define a lookup relationship on that object 
D. Create a view of objects and relationships without fields 

Answer: B C 

---
QUESTION 86 
Which two are true regarding a Dyno? Choose 2 answers 

A. Is a light weight VM used to run code on the Heroku Platform 
B. Has the ability to sleep as a standard and performance Dyno 
C. Is a lightweight Linux container used in a collection to run Heroku applications 
D. Has Ephemeral filesystems and is rebooted every 24 hours. 

Answer: C D 

---
QUESTION 87 
Which statement should a developer avoid using inside procedural loops? (Choose 2) 

A. System.debug('Amount of CPU time (in ms) used so far: ' + Limits.getCpuTime() ); 
B. List contacts = [SELECT Id, Salutation, FirstName, LastName, Email FROM Contact WHERE AccountId = :a.Id]; 
C. If(o.accountId == a.id) 
D. Update contactList; 

Answer: B D 

---
QUESTION 88 
What is a correct pattern to follow when programming in Apex on a Multi-tenant platform? 

A. Apex code is created in a separate environment from schema to reduce deployment errors. 
B. DML is performed on one record at a time to avoid possible data concurrency issues. 
C. Queries select the fewest fields and records possible to avoid exceeding governor limits. 
D. Apex classes use the ''with sharing" keyword to prevent access from other server tenants. 

Answer: C 

---
QUESTION 89 
What is the proper process for an Apex Unit Test 

A. Query for test data using SeeAllData = true. Call the method being tested. Verify that the results are correct. 
B. Query for test data using SeeAllData = true. Execute runAllTests(). Verify that the results are correct. 
C. Create data for testing. Execute runAllTests(). Verify that the results are correct. 
D. Create data for testing. Call the method being tested. Verify that the results are correct. 

Answer: D 

---
QUESTION 90 
Which statement would a developer use when creating test data for products and pricebooks? 

A. Id pricebookId = Test.getStandardPricebookId(); 
B. Pricebook pb = new Pricebook(); 
C. IsTest(SeeAllData = false); 
D. List objList = Test.loadData(Account.sObjectType, 'myResource'); 

Answer: A 

---
QUESTION 91 
What is true for a partial sandbox that is not true for a full sandbox? Choose 2 answers: 

A. More frequent refreshes. 
B. Only Includes necessary metadata. 
C. Use of change sets. 
D. Limited to 5 GB of data. 

Answer: A D 

---
QUESTION 92 
A developer creates an Apex class that includes private methods. What can the developer do to ensure that the private 
methods can be accessed by the test class? 

A. Add the TestVisible attribute to the Apex class 
B. Add the SeeAllData attribute to the test methods. 
C. Add the TestVisible attribute to the apex methods. 
D. Add the SeeAllData attribute to the test class 

Answer: C 

---
QUESTION 93 
Which option would a developer use to display the Accounts created in the current week and the number of related 
Contacts using a debug statement in Apex? 

A. For(Account acc: [SELECT Id, Name,(SELECT Id, Name FROM Contacts) FROM Account WHERE CreatedDate = 
THIS_WEEK]) { List cons = acc.Contacts; System.debug(acc.Name + ‘ has ’ + cons.size() + ‘Contacts’; } 
B. For(Account acc: [SELECT Id, Name, (SELECT Id, Name FROM Contacts) FROM Account WHERE CreatedDate =
CURRENT_WEEK]){ List cons = acc.Contacts; System.debug(acc.Name + ‘ has ‘ + cons.size() + ‘Contacts’); } 
C. For(Account acc:[SELECT Id, Name, Account.Contacts FROM Account WHERE CreatedDate = 
CURRENT_WEEK]) { List cons = acc.Account.Contacts; System.debug(acc.Name + ‘ has ‘ + cons.size() + 
‘Contacts’); } 
D. For(Account acc: [SELECT Id, Name, Account.Contacts FROM Account WHERE CreatedDate = 
THIS_WEEK]){ List cons = acc.Account.Contacts; System.debug(acc.Name + ‘ has ‘ + cons.size() + ‘Contacts’ } 

Answer: A 

---
QUESTION 94 
How can a developer avoid exceeding governor limits when using an Apex Trigger?choose 2 answers 

A. By using a helper class that can be invoked from multiple triggers. 
B. By using the Database class to handle DML transactions. 
C. By using Maps to hold data from query results. 
D. By performing DML transactions on lists of SObjects. 

Answer: C D 

---
QUESTION 95 
When creating unit tests in Apex, which statement is accurate?Choose 2 

A. Unit tests with multiple methods result in all methods failing every time one method fails. 
B. Increased test coverage requires large test classes with many lines of code in one method. 
C. Triggers do not require any unit tests in order to deploy them from sandbox to production. 
D. System Assert statements that do not Increase code coverage contribute important feedback in unit tests 

Answer: B D 

---
QUESTION 96 
Which scenario is invalid for execution by unit tests? 

A. Executing methods for negative test scenarios 
B. Loading the standard Pricebook ID using a system method 
C. Loading test data in place of user input for Flows. 
D. Executing methods as different users. 

Answer: C 

---
QUESTION 97 
When creating a record with a Quick Action, what is the easiest way to post a feed item? 

A. By selecting create feed item on the quick action. 
B. By adding a trigger on the new record. 
C. By adding a workflow rule on the new record. 
D. By selecting create case feed on the new record. 

Answer: A 

---
QUESTION 98 
A developer creates a method in an Apex class and needs to ensure that errors are handled properly.What would the 
developer use? (There are three correct answers.) 

A. ApexPages.addErrorMessage() 
B. A custom exception 
C. .addError() 
D. Database.handleException() 
E. A try/catch construct 

Answer: B C E 

---
QUESTION 99 
What is a valid source and destination pair that can send or receive change sets? (Choose 2) 

A. Developer Edition to Sandbox 
B. Sandbox to Production 
C. Sandbox to Sandbox 
D. Developer Edition to Production 

Answer: B C 

---
QUESTION 100 
Which resource can be included in a Lightning Component bundle? Choose 2 answers 

A. Apex class 
B. Adobe Flash 
C. JavaScript 
D. Documentation 

Answer: C D 

---
QUESTION 101 
How can a developer retrieve all Opportunity record type labels to populate a list collection?Choose 2 answers 

A. Obtain describe object results for the Opportunity objct. 
B. Write a for loop that extracts values from the Opportunity.RecordType.Name field. 
C. Use the global variable $RecordType and extract a list from the map. 
D. Write a SOQL for loop that iterates on the RecordType object. 

Answer: A D 

---
QUESTION 102 
In which order does Salesforce execute events upon saving a record? 

A. Before Triggers; Validation Rules; After Triggers; Assignment Rules; Workflow Rules; Commit 
B. Validation Rules; Before Triggers; After Triggers; Workflow Rules; Assignment Rules; Commit 
C. Before Triggers; Validation Rules; After Triggers; Workflow Rules; Assignment Rules; Commit 
D. Validation Rules; Before Triggers; After Triggers; Assignment Rules; Workflow Rules; Commit 

Answer: A 

---
QUESTION 103 
Which code segment can be used to control when the dowork() method is called? 

A. For (Trigger.isRunning t: Trigger.new) { dowork(); } 
B. If(Trigger.isRunning) dowork(); 
C. For (Trigger.isInsert t: Trigger.new) { dowork(); } 
D. If(Trigger.isInsert) dowork(); 

Answer: D 

---
QUESTION 104 
What is a valid way of loading external JavaScript files into a Visualforce page? (Choose 2) 

A. Using an (apex:includeScript)* tag. \> 
B. Using an (apex:define)* tag. 
C. Using a (link)* tag. 
D. Using a (script)* tag. 

Answer: A D 

---
QUESTION 105 
Where would a developer build a managed package? 

A. Developer Sandbox 
B. Unlimited Edition 
C. Partial Copy Sandbox 
D. Developer Edition 

Answer: D 

---
QUESTION 106 
Which code block returns the ListView of an Account object using the following debug statement? 
system.debug(controller.getListViewOptions() ); 

A. ApexPages.StandardSetController controller = new ApexPages.StandardSetController( 
Database.getQueryLocator( 'SELECT Id FROM Account LIMIT 1')); 
B. ApexPages.StandardController controller = new ApexPages.StandardController( [SELECT Id FROM Account LIMIT 
1]); 
C. ApexPages.StandardController controller = new 
ApexPages.StandardController( Database.getQueryLocator( 'SELECT Id FROM Account LIMIT 1')); 
D. ApexPages.StandardController controller = new ApexPages.StandardController( [SELECT Id FROM Account LIMIT 
1]); 

Answer: A 

---
QUESTION 107 
Which type of information is provided by the Checkpoints tab in the Developer Console? (Choose 2) 

A. Namespace 
B. Time 
C. Exception 
D. Debug Statement 

Answer: A B 

---
QUESTION 108 
What can a Lightning Component contain in its resource bundle? Choose 2 answer 

A. Custom client side rendering behavior. 
B. Build scripts for minification 
C. Properties files with global settings 
D. CSS styles scoped to the component 

Answer: A D 

---
QUESTION 109 
Developer needs to automatically populate the Reports To field in a Contact record based on the values of the related 
Account and Department fields in the Contact record. Which type of trigger would the developer create? Choose 2 
answers 

A. Before update 
B. After insert 
C. Before insert 
D. After update 

Answer: A C 

---
QUESTION 110 
A developer wants to display all of the available record types for a Case object. The developer also wants to display the 
picklist values for the Case.Status field. The Case object and the Case.Status field are on a custom Visualforce page. 
Which action can the developer perform to get the record types and picklist values in the controller? (Choose 2) 

A. Use Schema.PicklistEntry returned by Case.Status.getDescribe().getPicklistValues(). 
B. Use Schema.RecordTypeInfo returned by Case.sObjectType.getDescribe().getRecordTypeInfos(). 
C. Use SOQL to query Case records in the org to get all the RecordType values available for Case. 
D. Use SOQL to query case records in the org to get all values for the Status picklist field. 

Answer: A B 

---
QUESTION 111 
Where can debug log filter settings be set?Choose 2 answers 

A. The Filters link by the monitored user's name within the web UI. 
B. The Show More link on the debug log's record. 
C. On the monitored user's name. 
D. The Log Filters tab on a class or trigger detail page. 

Answer: A D 

---
QUESTION 112 
A company that uses a Custom object to track candidates would like to send candidate information automatically to a 
third -party human resource system when a candidate is hired. What can a developer do to accomplish this task? 

A. Create an escalation rule to the hiring manager.
B. Create an auto response rule to the candidate. 
C. Create a Process Builder with an outbound message action. 
D. Create a workflow rule with an outbound message action. 

Answer: D 

---
QUESTION 113 
A Hierarchy Custom Setting stores a specific URL for each profile in Salesforce. Which statement can a developer use to 
retrieve the correct URL for the current user'sprofile and display this on a Visualforce Page? 

A. {!$Setup.Url_Settings__C.Instance[Profile.Id].URL__c} 
B. {!$Setup.Url_Settings__C.URL__c} 
C. {!$Setup.Url_Settings__C.[Profile.Id].URL__c} 
D. {!$Setup.Url_Settings__C.[$Profile.Id].URL__c} 

Answer: B 

---
QUESTION 114 
A developer created an Apex trigger using the Developer Console and now wants to debug codeHow can the developer 
accomplish this in the Developer Console? 

A. Select the Override Log Triggers checkbox for the trigger 
B. Add the user name in the Log Inspector. 
C. Open the Progress tab in the Developer Console. 
D. Open the logs tab in the Developer Console. 

Answer: D 

---
QUESTION 115 
What would a developer do to update a picklist field on related Opportunity records when a modification to the 
associated Account record is detected? 

A. Create a process with Process Builder. 
B. Create a workflow rule with a field update. 
C. Create a Lightning Component. 
D. Create a Visualforce page. 

Answer: A 

---
QUESTION 116 
The initial value for a number field on a record is 1. A user updated the value of the number field to 10. This action 
invokes a workflow field update, which changes the value of the number field to 11. After the workflow field update, an 
update trigger fires.What is the value of the number field of the object that is obtained from Trigger.old? 

A. Null 
B. 11 
C. 1 
D. 10 

Answer: C 

---
QUESTION 117 
A developer needs to write a method that searches for a phone number that could be on multiple object types. Which 
method should the developer use to accomplish this task? 

A. SOQL Query that includes ALL ROWS 
B. SOQL query on each object 
C. SOSL Query that includes ALL ROWS 
D. SOSL query on each object 

Answer: C 

---
QUESTION 118 
Which requirement needs to be implemented by using standard workflow instead of Process Builder? Choose 
2 answers 

A. Create activities at multiple intervals. 
B. Send an outbound message without Apex code. 
C. Copy an account address to its contacts. 
D. Submit a contract for approval. 

Answer: B C 

---
QUESTION 119 
Before putting an app into production, which step should be taken? 

A. Run the production check feature via the web interface 
B. Switch to a production database 
C. Insure that you have installed a performance introspection add-on 
D. Scale your dynos 

Answer: A 

---
QUESTION 120 
What is a capability of the Force.com IDE? Choose 2 answers 

A. Roll back deployments. 
B. Run Apex tests. 
C. Download debug logs. 
D. Edit metadata components. 

Answer: B D 

---
QUESTION 121 
A developer needs to know if all tests currently pass in a Salesforce environment. Which feature can the developer use? 
(Choose 2) 

A. ANT Migration Tool 
B. Workbench Metadata Retrieval 
C. Salesforce UI Apex Test Execution 
D. Developer Console 

Answer: C D 

---
QUESTION 122 
Which two number expression evaluate correctly? Choose 2 answers 

A. Integer I = 3.14159; 
B. Decimal D = 3.14159; 
C. Long I = 3.14159; 
D. Double D =3.14159; 

Answer: B D 

---
QUESTION 123 
What is the minimum log level needed to see user-generated debug statements? 

A. DEBUG 
B. FINE 
C. INFO 
D. WARN 

Answer: A 

---
QUESTION 124 
A visualforce interface is created for Case Management that includes both standard and custom functionality defined in 
an Apex class called myControllerExtension. The visualforce page should include which <apex:page> attribute(s) to 
correctly implement controller functionality? 

A. StandardController = "case" and extensions =" myControllerExtension" 
B. Extensions=" myControllerExtension" 
C. Controller=" myControllerExtension" 
D. Controller = "case" and extensions =" myControllerExtension" 

Answer: A 

---
QUESTION 125 
What must the Controller for a Visualforce page utilize to override the Standard Opportunity view button? 

A. The StandardSetController to support related lists for pagination. 
B. The Opportunity StandardController for pre -built functionality. 
C. A callback constructor to reference the StandardController. 
D. A constructor that initializes a private Opportunity variable. 

Answer: B 

---
QUESTION 126 
A reviewer is required to enter a reason in the comments field only when a candidate is recommended to be hired. Which 
action can a developer take to enforce this requirement? 

A. Create a required Visualforce component. 
B. Create a formula field. 
C. Create a required comments field. 
D. Create a validation rule. 

Answer: D 

---
QUESTION 127 
Where can the custom roll-up summary fields be created using Standard Object relationships (Choose 3) 

A. On Opportunity using Opportunity Product records. 
B. On Account using Case records. 
C. On Quote using Order records. 
D. On Campaign using Campaign Member records. 
E. On Account using Opportunity records. 

Answer: A D E 

---
QUESTION 128 
How would a developer change the field type of a custom field on the Account object from string to an integer? 

A. Make the changes in the developer console, and then the change will automatically be reflected in the Apex code. 
B. Mate the change in the declarative UI, then update the field type to an integer field in the Apex code. 
C. Make the change in the declarative UI, an then the change will automatically be reflected in the Apex code. 
D. Remove all references in the code, make the change in the declarative UI, and restore the references with the new type. 

Answer: D 

---
QUESTION 129 
What is the accurate statement about with sharing keyword? choose 2 answers 

A. Inner class do not inherit the sharing setting from the container class 
B. Both inner and outer class can be declared as with sharing 
C. Either inner class or outer classes can be declared as with sharing but not both 
D. Inner class inherit the sharing setting from the container class 

Answer: A B 

---
QUESTION 130 
What is a valid Apex statement? 

A. Map conMap = (SELECT Name FROM Contact); 
B. Account[] acctList = new List{new Account()} 
C. Integer w, x, y = 123, z = 'abc', 
D. Private static constant Double rate = 775; 

Answer: B 

---
QUESTION 131 
Which user can edit a record after it has been locked for approval? (Choose 2) 

A. Any user with a higher role in the hierarchy 
B. A user who is assigned as the current approver 
C. Any user who approved the record previously 
D. An administrator 

Answer: B D 

---
QUESTION 132 
A company would like to send an offer letter to a candidate, have the candidate sign it electronically, and then send the 
letter back.What can a developer do to accomplish this? 

A. Create a visual workflow that will capture the candidate’s signature electronically 
B. Develop a Process Builder that will send the offer letter and allow the candidate to sign it electronically. 
C. Install a managed package that will allow the candidate to sign documents electronically 
D. Create an assignment rule that will assign the offer letter to the candidate 

Answer: C 

---
QUESTION 133 
What is the easiest way to verify a user before showing them sensitive content? 

A. Sending the user a SMS message with a passcode. 
B. Calling the generateVerificationUrl method in apex. 
C. Sending the user an Email message with a passcode. 
D. Calling the Session.forcedLoginUrl method in apex. 

Answer: B 

---
QUESTION 134 
Which standard field needs to be populated when a developer inserts new Contact records programmatically? 

A. Accountld 
B. Name 
C. LastName 
D. FirstName 

Answer: C 

---
QUESTION 135 
A developer creates an Apex helper class to handle complex trigger logic. How can the helper class warn users when the 
trigger exceeds DML governor limits? 

A. By using PageReference.setRedirect() to redirect the user to a custom Visualforce page before the number of DML 
statements is exceeded. 
B. By using Messaging.sendEmail() to continue toe transaction and send an alert to the user after the number of DML 
statements is exceeded. 
C. By using AmexMessage.Messages() to display an error message after the number of DML statements is exceeded. 
D. By using Limits.getDMLRows() and then displaying an error message before the number of DML statements is 
exceeded. 

Answer: D 

---
QUESTION 136 
A developer is creating an application to track engines and their parts. An individual part can be used in different types 
of engines.What data model should be used to track the data and to prevent orphan records? 

A. Create a junction object to relate many engines to many parts through a master-detail relationship 
B. Create a lookup relationship to represent how each part relates to the parent engine object. 
C. Create a master-detail relationship to represent the one-to-many model of engines to parts. 
D. Create a junction object to relate many engines to many parts through a lookup relationship 

Answer: A 

---
QUESTION 137 
What are the supported content sources for custom buttons and links? (Choose 2 Answers) 

A. VisualForce Page. 
B. Static Resource. 
C. URL. 
D. Chatter File. 
E. Lightning Page. 

Answer: A C 

---
QUESTION 138 
What is a characteristic of the Lightning Component Framework? Choose 2 answers: 

A. It has an event-driven architecture. 
B. It works with existing Visualforce pages. 
C. It includes responsive components. 
D. It uses XML as its data format. 

Answer: A C 

---
QUESTION 139 
What is a capability of formula fields? (Choose 3) 

A. Generate a link using the HYPERLINK function to a specific record in a legacy system. 
B. Display the previous values for a field using the PRIORVALUE function. 
C. Return and display a field value from another object using the VLOOKUP function. 
D. Determine if a datetime field has passed using the NOW function. 
E. Determine which of three different images to display using the IF function. 

Answer: A D E 

---
QUESTION 140 
In the Lightning Component framework, where is client-side controller logic contained? 

A. Apex 
B. Visualforce 
C. HTML 
D. JavaScript 

Answer: D 

---
QUESTION 141 
What is the return data type when ApexPages.currentPage().getParameters() is used to retrieve URL parameters from a 
visualforce controller? 

A. Map 
B. List 
C. Enum 
D. String[] 

Answer: A 

---
QUESTION 142 
Given the code block: Integer x; For(x=0;x<10; x+=2) { If(x==8) break; If(x==10) break; } System.debug(x); Which 
value will the system debug statement display? 

A. 2 
B. 10 
C. 8 
D. 4 

Answer: C 

---
QUESTION 143 
A developer needs to confirm that an Account trigger is working correctly without changing the organization’s 
data.What would the developer do to test the Account trigger? 

A. Use the Test menu on the developer Console to run all test classes for the account trigger. 
B. Use the New button on the Salesforce Accounts Tab to create a new Account record. 
C. Use the Open Execute Anonymous feature on the Developer Console to run an ‘insert Account’ DML statement. 
D. Use Deply from the Force.com IDE to deploy an ‘insert Account’ Apex class. 

Answer: A 

---
QUESTION 144 
A Visual force page displays two fields named Phone Number and Email.User1 has access to Phone Number, but not to 
Email.User2 has access to Email, but not Phone NumberA developer needs to ensure that User1 can 
only see Phone Number, and User2 can only see Email.Which method can the developer use to achieve this? 

A. Schema isUpdateable() method. 
B. Schema isAccessible() method. 
C. Schema isReadable() method. 
D. Schema isCreateable() method. 

Answer: B 

---
QUESTION 145 
What is the result of the following code block ? 
Integer x = 1;Integer Y = 0;While(x < 10){Y++;} 

A. An error occurs 
B. Y = 9 
C. Y = 10 
D. X = 0 

Answer: A 

---
QUESTION 146 
A candidate may apply to multiple jobs at the company Universal Containers by submitting a single application per job 
posting, that application cannot be modified to be resubmitted to a different job posting.What can the administrator do to 
associate an application with each job posting in the schema for the organization? 

A. Create a lookup relationship on both objects to a junction object called Job Posting Applications. 
B. Create a master-detail relationship in the Job Postings custom object to the Applications custom object. 
C. Create a master-detail relationship in the Application custom object to the Job Postings custom object. 
D. Create a lookup relationship in the Applications custom object to the Job Postings custom object. 

Answer: C 

---
QUESTION 147 
When would a developer use a custom controller instead of a controller extension? Choose 2 answers: 

A. When a Visualforce page needs to replace the functionality of a standard controller. 
B. When a Visualforce page does not reference a single primary object. 
C. When a Visualforce page should not enforce permissions or field-level security. 
D. When a Visualforce page needs to add new actions to a standard controller. 

Answer: B C 

---
QUESTION 148 
In an organization that has enabled multiple currencies, a developer needs to aggregate the sum of the
Estimated_value__c currency field from the CampaignMember object using a roll-up summary field called 
Total_estimated_value__c on Campaign. 

A. The values in Campaignmember.Estimated_value__c are converted into the currency of the Campaign record and the 
sum is displayed using the currency on the Campaign record. 
B. The values in CampaignMember.Estimated_value__c are converted into the currency on the majority of the 
CampaignMember records and the sum is displayed using that currency. 
C. The values in CampaignMember.Estimated_value__c are summed up and the resulting Total_estimated_value__c 
field is displayed as a numeric field on the Campaign record. 
D. The values In CampaignMember.Estimated_value__c are converted into the currency of the current user, and the sum 
is displayed using the currency on the Campaign record. 

Answer: A 

---
QUESTION 149 
The Sales Management team hires a new intern. The intern is not allowed to view Opportunities, but needs to see the 
Most Recent Closed Date of all child Opportunities when viewing an Account record. What would a 
developer do to meet this requirement? 

A. Create a trigger on the Account object that queries the Close Date of the most recent Opportunities. 
B. Create a Workflow rule on the Opportunity object that updates a field on the parent Account. 
C. Create a formula field on the Account object that performs a MAX on the Opportunity Close Date field. 
D. Create a roll-up summary field on the Account object that performs a MAX on the Opportunity Close Date field. 

Answer: D 

---
QUESTION 150 
What is an important consideration when developing in a multi-tenant environment? 

A. Governor limits prevent tenants from impacting performance in multiple orgs on the same instance. 
B. Unique domain names take the place of namespaces for code developed for multiple orgs on multiple instances. 
C. Polyglot persistence provides support for a global, multilingual user base in multiple orgs on multiple instances. 
D. Org-wide data security determines whether other tenants can see data in multiple orgs on the same instance. 

Answer: A 

---
QUESTION 151 
A developer in a Salesforce org with 100 Accounts executes the following code using the Developer console: Account 
myAccount = new Account(Name = 'MyAccount');Insert myAccount;For (Integer x = 0; x < 250; x++) 
{Account newAccount = new Account (Name='MyAccount' + x);try {Insert newAccount;}catch (Exception ex) 
{System.debug (ex) ;}}insert new Account (Name='myAccount'); How many accounts are in the org after this code is 
run? 

A. 101 
B. 100 
C. 102 
D. 252 

Answer: B 

---
QUESTION 152 
A developer wants to display all of the available record types for a Case object. The developer also wants to display the 
picklist values for the Case.Status field. The Case object and the Case Status field are on a custom visualforce page. 
Which action can the developer perform to get the record types and picklist values in the controller? Choose 2 answers 

A. Use Schema.PicklistEntry returned by Case Status getDescribe().getPicklistValues(). 
B. Use Schema.RecordTypeinfo returned by Case.SObjectType getDescribe().getRecordTypelnfos() 
C. Use SOQL to query Case records in the org to get all the RecordType values available for Case. 
D. Use SOQL to query Case records in the org to get all value for the Status picklist field. 

Answer: A B 

---
QUESTION 153 
Why would a developer use Test. startTest( ) and Test.stopTest( )? 

A. To avoid Apex code coverage requirements for the code between these lines 
B. To start and stop anonymous block execution when executing anonymous Apex code 
C. To indicate test code so that it does not Impact Apex line count governor limits. 
D. To create an additional set of governor limits during the execution of a single test class. 

Answer: D 

---
QUESTION 154 
A candidate may apply to multiple jobs at the company Universal Containers by submtting a single application per job 
posting. Once an application is submitted for a job posting, that application cannot be modified to be
resubmitted to a different job posting.What can the administrator do to associate an application with each job posting in 
the schema for the organization? 

A. Create a master-detail relationship in the Job Postings custom object to the Applications custom object. 
B. Create a master-detail relationship in the Application custom object to the Job Postings custom object. 
C. Create a lookup relationship on both objects to a junction object called Job Posting Applications. 
D. Create a lookup relationship in the Applications custom object to the Job Postings custom object 

Answer: A 

---
QUESTION 155 
Which Apex collection is used to ensure that all values are unique? 

A. A Set 
B. An Enum 
C. A List 
D. An sObject 

Answer: A 

---
QUESTION 156 
A developer runs the following anonymous code block:List<Account> acc = [SELECT Id FROM Account LIMIT 
10];Delete acc;Database.emptyRecycleBin(acc);system.debug(Limits.getDMLStatements()+ ‘, ‘ 
+Limits.getLimitDMLStatements());What is the result? 

A. 11, 150 
B. 150, 2 
C. 150, 11 
D. 2, 150 

Answer: D 

---
QUESTION 157 
A developer has the following query: Contact c = [SELECT id, firstname, lastname, email FROM Contact WHERE 
lastname = 'Smith']; What does the query return if there is no Contact with the last name 'Smith'? 

A. A contact initialized to null. 
B. An error that no rows are found. 
C. An empty List of Contacts. 
D. A Contact with empty values. 

Answer: B 

---
QUESTION 158 
On which object can an administrator create a roll-up summary field? 

A. Any object that is on the master side of a master-detail relationship. 
B. Any object that is on the parent side of a lookup relationship. 
C. Any object that is on the detail side of a master-detail relationship. 
D. Any object that is on the child side of a lookup relationship. 

Answer: A 

---
QUESTION 159 
A developer has a block of code that omits any statements that indicate whether the code block should execute with or 
without sharing. What will automatically obey the organization-wide defaults and sharing settings for 
the user who executes the code in the Salesforce organization? 

A. Apex Triggers 
B. HTTP Callouts 
C. Apex Controllers 
D. Anonymous Blocks 

Answer: D 

---
QUESTION 160 
A developer has the following code block: 
public class PaymentTax {public static decimal SalesTax = 0.0875;} trigger OpportunityLineItemTrigger on 
OpportunityLineItem (before insert, before update) {PaymentTax PayTax = new PaymentTax();decimal ProductTax = 
ProductCost * XXXXXXXXXXX;} To calculate the productTax, which code segment would a developer insert at the 
XXXXXXXXXXX to make the value the class variable SalesTax accessible within the trigger? 

A. SalesTax 
B. PayTax.SalesTax 
C. PaymentTax.SalesTax 
D. OpportunityLineItemTngger.SalesTax 

Answer: C 

---
QUESTION 161 
An sObject named Application_c has a lookup relationship to another sObject named Position_c. Both Application _c 
and Position_c have a picklist field named Status_c.When the Status_c field on Position_c is updated, the Status_c field 
on Application_c needs to be populated automatically with the same value, and execute a workflow rule on 
Application_c.How can a developer accomplish this? 

A. By changing Application_c.Status_c into a roll -up summary field. 
B. By changing Application_c.Status_c into a formula field. 
C. By using an Apex trigger with a DML operation. 
D. By configuring a cross-object field update with a workflow. 

Answer: C 

---
QUESTION 162 
A developer has the following trigger that fires after insert and creates a child Case whenever a new Case is created. 
List<Case> childCases = new List<Case>();for (Case parent : Trigger.new){Case child = new Case (ParentId = parent.Id, 
Subject = parent.Subject);childCases.add(child);}insert childCases; What happens after the code block executes? 

A. Multiple child cases are created for each parent case in Trigger.new. 
B. Child case is created for each parent case in Trigger.new. 
C. The trigger enters an infinite loop and eventually fails. 
D. The trigger fails if the Subject field on the parent is blank. 

Answer: B 

---
QUESTION 163 
How would a developer determine if a CustomObject__c record has been manually shared with the current user in Apex? 

A. By querying the role hierarchy. 
B. By calling the isShared() method for the record. 
C. By querying CustomObject__Share. 
D. By calling the profile settings of the current user. 

Answer: C 

---
QUESTION 164 
Which data structure is returned to a developer when performing a SOSL search? 

A. A list of lists of sObjects. 
B. A map of sObject types to a list of sObjects 
C. A map of sObject types to a list oflists of sobjects 
D. A list of sObjects. 

Answer: A 

---
QUESTION 165 
In the code below, what type does Boolean inherit from? 
Boolean b= true; 

A. Enum 
B. Object 
C. String 
D. Class 

Answer: B 

---
QUESTION 166 
A developer executes the following code in the Developer Console: 
List<Account> fList = new List <Account> ();For(integer i= 1; I <= 200; i++){fList.add(new Account ( Name = 
‘Universal Account ‘ + i));}Insert fList;List <Account> sList = new List<Account>();For (integer I = 201; I <= 
20000; i ++){sList.add(new Account (Name = ‘Universal Account ‘ + i));}Insert sList;How many accounts are created in 
the Salesforce organization ? 

A. 20000 
B. 0 
C. 200 
D. 1000 

Answer: B 

---
QUESTION 167 
A developer writes a SOQL query to find child records for a specific parent. How many levels can be returned in a single 
query? 

A. 1 
B. 7 
C. 5 
D. 3 

Answer: C 

---
QUESTION 168 
To which primitive data type in Apex is a currency field atomically assigned? 

A. Integer 
B. Decimal 
C. Double 
D. Currency 

Answer: B 

---
QUESTION 169 
What are two correct examples of the model in the salesforce MVC architecture? Choose 2 answers. 

A. Custom field on the custom wizard_c object 
B. Standard lightning component 
C. Workflow rule on the contact object 
D. Standard account lookup on the contract object 

Answer: B C 

---
QUESTION 170 
In a single record, a user selects multiple values from a multi-select picklist. How are the selected values represented in 
Apex? 

A. As a String with each value separated by a comma 
B. As a Set with each value as an element in the set 
C. As a String with each value separated by a semicolon 
D. As a List with each value as an element in the list Previous 

Answer: C 

---
QUESTION 171 
What is a valid statement about Apex classes and interfaces? Choose 2 answers: 

A. The default modifier for a class is private. 
B. Exception classes must end with the word exception. 
C. A class can have multiple levels of inner classes. 
D. The default modifier for an interface is private. 

Answer: B D 

---
QUESTION 172 
How can a developer avoid exceeding governor limits when using Apex Triggers? (Choose 2) 

A. By using a helper class that can be invoked from multiple triggers 
B. By using Maps to hold data from query results 
C. By using the Database class to handle DML transactions 
D. By performing DML transactions on a list of sObjects. 

Answer: B D 

---
QUESTION 173 
A company wants a recruiting app that models candidates and interviews; displays the total number of interviews on 
each candidate record; and defines security on interview records that is independent from the security
on candidate records. What would a developer do to accomplish this task? Choose 2 answers 

A. Create a roll -up summary field on the Candidate object that counts Interview records. 
B. Create a master -detail relationship between the Candidate and Interview objects. 
C. Create a lookup relationship between the Candidate and Interview objects. 
D. Create a trigger on the Interview object that updates a field on the Candidate object. 

Answer: C D 

---
QUESTION 174 
Which component is available to deploy using Metadata API? Choose 2 answers 

A. Case Layout 
B. Account Layout 
C. Case Feed Layout 
D. ConsoleLayout 

Answer: A B 

---
QUESTION 175 
Which action can a developer perform in a before update trigger? (Choose 2) 

A. Display a custom error message in the application interface. 
B. Change field values using the Trigger.new context variable. 
C. Delete the original object using a delete DML operation. 
D. Update the original object using an update DML operation. 

Answer: A B 

---
QUESTION 176 
What is a capability of the Developer Console? 

A. Execute Anonymous Apex code, Create/Edit code, view Debug Logs. 
B. Execute Anonymous Apex code, Run REST API, create/Edit code. 
C. Execute Anonymous Apex code, Create/Edit code, Deploy code changes. 
D. Execute Anonymous Apex code, Run REST API, deploy code changes. 

Answer: A 

---
QUESTION 177 
A developer uses a before insert trigger on the Lead object to fetch the Territory__c object, where the 
Territory__c.PostalCode__c matches the Lead.PostalCode. The code fails when the developer uses the Apex Data 
Loader to insert 10,000 Lead records. The developer has the following code block: Line-01: for (Lead l : 
Trigger.new){Line-02: if (l.PostalCode != null) {Line-03: List<Territory__c> terrList = [SELECT Id FROM 
Territory__c WHERE PostalCode__c = :l.PostalCode];Line-04: if(terrList.size() > 0) Line-05: l.Territory__c = 
terrList[0].Id; Line-06: }Line-07: }Which line of code is causing the code block to fail? 

A. Line-03: A SOQL query is located inside of the for loop code. 
B. Line-01: Trigger:new is not valid in a before insert Trigger. 
C. Line-02: A NullPointer exception is thrown if PostalCode is null. 
D. Line-05: The Lead in a before insert trigger cannot be updated. 

Answer: A 

---
QUESTION 178 
What are two testing consideration when deploying code from a sandbox to production? Choose 2 answers 

A. 75% of test must execute without failure 
B. 100% of test must execute without failure 
C. Apex code requires 75% coverage 
D. Apex code requires 100% coverage 

Answer: B C 

---
QUESTION 179 
An org has different Apex Classes that provide Account -related functionality.After a new validation rule is added to the 
object, many of the test methods fail.What can be done to resolve the failures and reduce the 
number of code changes needed for future validation rules?Choose 2 answers: 

A. Create a method that creates valid Account records, and call this method from within test methods. 
B. Create a method that loads valid Account records from a Static Resource, and call this method within test methods. 
C. Create a method that performs a callout for a valid Account record, and call this method from within test methods. 
D. Create a method that queries for valid Account records, and call this method from within test methods. 

Answer: A B 

---
QUESTION 180 
A developer wants to create a custom object to track Customer Invoices.How should Invoices and Accounts be related to 
ensure that all Invoices are visible to everyone with access to an Account? 

A. The Account should have a Master-Detail relationship to the Invoice. 
B. The Invoice should have a Master-Detail relationship to the Account 
C. The Account should have a Lookup relationship to the Invoice 
D. The Invoice should have a Lookup relationship to the Account Previous 

Answer: B 

---
QUESTION 181 
How can a developer refer to, or instantiate a PageReference in Apex? Choose 2 answers 

A. By using a PageReference with a partial or full URL. 
B. By using the Page object and a Visualforce page name. 
C. By using the ApexPages.Page() method with a Visualforce page name. 
D. By using the PageReference.Page() method with a partial or full URL. 

Answer: A B 

---
QUESTION 182 
A developer tasked with creating a schema to track Movies, Actors, and contracts. A single movie can have many 
contracts and a single actor can have many contracts. Each contract is owned and actively managed by a single user. 
Which schema should be created to enable user to easily manage the contract they own; without requiring access to the 
movie or the actor records? 

A. A master detail relationship to the movie object and a lookup relationship to the actor object 
B. A lookup relationship to the movie object and a lookup relationship to the actor object 
C. A lookup relationship to the movie object and a master detail relationship to the actor object 
D. A master detail relationship to the movie object and a master detail relationship to the actor object 

Answer: B 

---
QUESTION 183 
A developer creates a new Visualforce page and Apex extension, and writes test classes that exercise 95% coverage of 
the new Apex extension.Change set deployment to production fails with the test coverage warning: "Average test 
coverage across all Apex classes and triggers is 74%, at least 75% test coverage is required."What can the developer do 
to successfully deploy the new Visualforce page and extension? 

A. Create test classes to exercise the Visualforce page markup. 
B. Select "Disable Parallel Apex Testing" to run all the tests. 
C. Add test methods to existing test classes from previous deployments. 
D. Select "Fast Deployment'' to bypass running all the tests. 

Answer: C 

---
QUESTION 184 
A developer created a lightning component name accountList.cmp that display a list of Accounts. Client-side logic that is 
executed when a user hovers over an account in the list should be stored in which bundle member? 

A. AccountListHelper.js 
B. AccountListRenderer.js 
C. AccountList.renderer 
D. AccountList.helper 

Answer: C 

---
QUESTION 185 
What is a good practice for a developer to follow when writing a trigger? (Choose 2) 

A. Using @future methods to perform DML operations. 
B. Using the Map data structure to hold query results by ID. 
C. Using the Set data structure to ensure distinct records. 
D. Using synchronous callouts to call external systems. 

Answer: B C 

---
QUESTION 186 
Which two queries can a developer use in a visualforce controller to protect against SOQL injection Vulnerabilities? 
Choose 2 answers 

A. String qryName = '%' + String.enforceSecurityChecks(name)+ '%'; String qryString = 'SELECT Id FROM Contact 
WHERE Name LIKE :qryNAme'; List queryResults = Database.query(qryString); 
B. String qryName = '%' + name '%'; String qryString = 'SELECT Id FROM Contact WHERE Name LIKE :qryNAme'; 
List queryResults = Database.query(qryString); 
C. String qryName = '%' + String.escpaeSingleQuotes(name)+ '%'; String qryString = 'SELECT Id FROM Contact 
WHERE Name LIKE :qryNAme'; List queryResults = Database.query(qryString); 
D. String qryString = 'SELECT Id FROM Contact WHERE Name LIKE :qryNAme'; List queryResults = 
Database.query(qryString); 

Answer: A D 

---
QUESTION 187 
When the number of record in a recordset is unknown, which control statement should a developer use to implement a 
set of code that executes for every record in the recordset, without performing a .size() or 
.length() method call? 

A. For (init_stmt, exit_condition; increment_stmt) { } 
B. Do { } While (Condition) 
C. For (variable : list_or_set) { } 
D. While (Condition) { ... } 

Answer: C 

---
QUESTION 188 
How can a developer determine, from the DescribeSObjectResult, if the current user will be able to create records for an 
object in Apex? 

A. By using the isInsertable() method. 
B. By using the isCreatable() method. 
C. By using the hasAccess() method. 
D. By using the canCreate() method. 

Answer: B 

---
QUESTION 189 
Which statement about the Lookup Relationship between a Custom Object and a Standard Object is correct? 

A. The Lookup Relationship on the Custom Object can prevent the deletion of the Standard Object. 
B. The Lookup Relationship cannot be marked as required on the page layout for the Custom Object. 
C. The Custom Object will be deleted when the referenced Standard Object is deleted. 
D. The Custom Object inherits security from the referenced Standard Objects 

Answer: C 

---
QUESTION 190 
A developer wrote a workflow email alert on case creation so that an email is sent to the case owner manager when a 
case is created. When will the email be sent? 

A. After Committing to database. 
B. Before Trigger execution. 
C. After Trigger execution. 
D. Before Committing to database. 

Answer: A 

---
QUESTION 191 
A Visualforce page has a standard controller for an object that has a lookup relationship to a parent object. How can a 
developer display data from the parent record on the page? 

A. By adding a second standard controller to the page for the parent record. 
B. By using a roll-up formula field on the child record to include data from the parent record. 
C. By using SOQL on the Visualforce page to query for data from the parent record. 
D. By using merge field syntax to retrieve data from the parent record. 

Answer: D 

---
QUESTION 192 
Which data type or collection of data types can SOQL statements populate or evaluate to? (Choose 3) 

A. A single sObject 
B. An integer 
C. A string 
D. A list of sObjects 
E. A Boolean 

Answer: A B D 

---
QUESTION 193 
What is the value of x after the code segment executes?String x = 'A';Integer i = 10;if ( i < 15 ) {i = 15;x = 'B';} else if ( i 
< 20 ) {x = 'C';} else {x = 'D'; } 

A. D 
B. A 
C. B 
D. C 

Answer: C 

---
QUESTION 194 
A developer needs to create a Visualforce page that will override the standard Account edit button. The page will be used 
to validate the account's address using a SOQL query. The page will also allow the user to make 
edits to the address. Where would the developer write the Account address verification logic? 

A. In a Standard Extension. 
B. In a Standard Controller. 
C. In a Custom Controller. 
D. In a Controller Extension. 

Answer: D 

---
QUESTION 195 
The Review_c object have a lookup relationship to the job_Application_c object. The job_Application_c object has a 
master detail relationship up to the position_c object. The relationship is based on the auto populated defaults? 
What is the recommended way to display field data from the related Review _C records a Visualforce page for a single 
Position_c record? Select one of the following: 

A. Utilize the Standard Controller for Position_c and cross-object Formula Fields on the Job_Application_c object to 
display Review_c data. 
B. Utilize the Standard Controller for Position_c and a Controller Extension to query for Review_c data. 
C. Utilize the Standard Controller for Position_c and expression syntax in the Page to display related Review_c through 
the Job_Applicacion_c inject. 
D. Utilize the Standard Controller for Position_c and cross-object Formula Fields on the Review_c object to display 
Review_c data. 

Answer: B 

---
QUESTION 196 
Which trigger event allows a developer to update fields in the Trigger.new list without using an additional DML 
statement?Choose 2 answers 

A. Before insert 
B. Before update 
C. After update 
D. After insert 

Answer: A B 

---
QUESTION 197 
A developer creates an Apex Trigger with the following code block:List<Account> customers = new 
List<Account>();For (Order__c o: trigger.new){Account a = [SELECT Id, Is_Customer__c FROM Account WHERE Id 
= 
:o.Customer__c];a.Is_Customer__c = true;customers.add(a);}Database.update(customers, false);The developer tests the 
code using Apex Data Loader and successfully loads 10 Orders. Then, the developer loads 150 
Orders.How many Orders are successfully loaded when the developer attempts to load the 150 Orders? 

A. 0 
B. 1 
C. 150 
D. 100 

Answer: A 

---
QUESTION 198 
A developer has the following code:try {List nameList;Account a;String s = a.Name;nameList.add(s);} catch 
(ListException le ) {System.debug(' List Exception ');} catch (NullPointerException npe) {System.debug(' 
NullPointer Exception ');} catch (Exception e) {System.debug(' Generic Exception ');} What message will be logged? 

A. List Exception 
B. NullPointer Exception 
C. Generic Exception 
D. No message is logged 

Answer: B 

---
QUESTION 199 
What is the preferred way to reference web content such as images, style sheets, JavaScript, and other libraries that is 
used in Visualforce pages? 

A. By accessing the content from Chatter Files. 
B. By uploading the content in the Documents tab. 
C. By accessing the content from a third -party CON. 
D. By uploading the content as a Static Resource. 

Answer: D 

---
QUESTION 200 
A developer in a Salesforce org with 100 Accounts executes the following code using the Developer console:Account 
myAccount = new Account(Name = 'MyAccount');Insert myAccount;For (Integer x = 0; x < 150; x++) 
{Account newAccount = new Account (Name='MyAccount' + x);try {Insert newAccount;} catch (Exception ex)
{System.debug (ex) ;}}insert new Account (Name='myAccount');How many accounts are in the org after this code is run?

A. 101 
B. 100 
C. 102 
D. 252 

Answer: B 

---
QUESTION 201 
When loading data into an operation, what can a developer do to match records to update existing records? (Choose 2) 

A. Match an auto-generated Number field to a column in the imported file. 
B. Match an external Id Text field to a column in the imported file. 
C. Match the Name field to a column in the imported file. 
D. Match the Id field to a column in the imported file. 

Answer: B D 

---
QUESTION 202 
A developer wants to list all of the Tasks for each Account on the Account detail page. When a task is created for a 
Contact, what does the developer need to do to display the Task on the related Account record? 

A. Nothing. The task is automatically displayed on the Account page. 
B. Nothing. The Task cannot be related to an Account and a Contact. 
C. Create a Workflow rule to relate the Task to the Contact's Account. 
D. Create an Account formula field that displays the Task information. 

Answer: A 

---
QUESTION 203 
A developer is creating a test coverage for a class and needs to insert records to validate functionality. Which method 
annotation should be used to create records for every method in the test class? 

A. @BeforeTest 
B. @isTest(SeeAllData=True) 
C. @TestSetup 
D. @PreTest 

Answer: C 

---
QUESTION 204 
What is an accurate statement about variable scope? (Choose 3) 

A. Parallel blocks can use the same variable name. 
B. A variable can be defined at any point in a block. 
C. Sub-blocks cannot reuse a parent block's variable name. 
D. Sub-blocks can reuse a parent block's variable name if it's value is null. 
E. A static variable can restrict the scope to the current block of its value is null. 

Answer: A B C 

---
QUESTION 205 
A developer writes a before insert trigger.How can the developer access the incoming records in the trigger body? 

A. By accessing the Trigger.new context variable. 
B. By accessing the Trigger.newRecords context variable. 
C. By accessing the Trigger.newMap context variable. 
D. By accessing the Tripper.newList context variable. 

Answer: A 

---
QUESTION 206 
In which two org types can a developer create new Apex Classes? Choose 2 answers 

A. Developer Edition 
B. Sandbox 
C. Enterprise Edition 
D. Unlimited 

Answer: A B 

---
QUESTION 207 
What is a capability of a StandardSetController?Choose 2 answers 

A. It allows pages to perform mass updates of records 
B. It allows pages to perform pagination with large record sets 
C. It enforces field-level security when reading large record sets 
D. It extends the functionality of a standard or custom controller 

Answer: A B 

---
QUESTION 208 
A developer needs to create records for the object Property__c. The developer creates the following code block:List 
propertiesToCreate = helperClass.createProperties();try { // line 3 } catch (Exception exp ) { //exception 
handling }Which line of code would the developer insert at line 3 to ensure that at least some records are created, even if 
a few records have errors and fail to be created? 

A. Database.insert(propertiesToCreate, false); 
B. insert propertiesToCreate; 
C. Database.insert(propertiesToCreate, System.ALLOW_PARTIAL); 
D. Database.insert(propertiesToCreate); 

Answer: A 

---
QUESTION 209 
Which declarative method helps ensure quality data? (Choose 3) 

A. Validation Rules 
B. Workflow alerts 
C. Exception Handling 
D. Lookup Filters 
E. Page Layouts 

Answer: A D E 

---
QUESTION 210 
A developer creates a custom controller and custom Visualforce page by using the following code block:public class 
myController {public String myString;public String getMyString() {return 'getmyString';}public String 
getStringMethod1() {return myString;}public String getStringMethod2() {if (myString == null)myString =
'Method2';return myString;}}{!myString}, {!StringMethod1}, {!StringMethod2}, {!myString}What does the user see 
when accessing the custom page? 

A. GetMyString , , Method2 , getMystring 
B. , , Method2 , getMyString 
C. , , Method2, 
D. GetMyString , , , 

Answer: A 

---
QUESTION 211 
What is a benefit of the lightning component framework? 

A. Better integration with Force.com sites 
B. Better performance for custom Salesforce1 Mobile Apps 
C. More Centralized control via server-side logic 
D. More pre-built components to replicate the salesforce look and feel 

Answer: D 