#### ```<apex:input>```

- 不对应于 Salesforce 字段或对象上的任何其他数据，因此需要自定义代码才能使用用户输入的值

- ```html
  <apex:inputfield value=”{!newAccount.website}”/>
  Account acc = new Account();acc.addError('Name', 'msg'); 字段加error
  ```

- ```html
  <apex:input value="{!inputValue}" id="theTextInput"/>
  // 上面的示例呈现以下 HTML：
  <input id="theTextInput" type="text" name="theTextInput" />
  ```

---

#### ```<apex:actionFunction>```

##### 特点：

- AJAX request

- must be a child of an ```<apex:form>``` component

- ```<apex:param>```  is matched by the caller's argument list.

- 可获取controller上sobject字段以外的input的值 （补充：只有`<apex:input>` `<apex:output>`能使用sobject项字段 ）

- `<apex:actionFunction>` 定义了一个新的JavaScript function 并且可以被别的JavaScript调用， 而`<apex:actionSupport >`不能

- 不能用于循环组件 `<apex:pageBlockTable>`, `<apex:repeat>`

- ```html
  <!-- Page: -->
  <apex:page controller="exampleCon">
      <apex:form>
          <!-- Define the JavaScript function sayHello-->
          <apex:actionFunction name="sayHello" action="{!sayHelloFromController}" rerender="out" status="myStatus"/>
  		</apex:form>
      <script>window.setTimeout(sayHello,2000)</script>
  </apex:page>
  ```

##### VS Comparing JavaScript Remoting

- The `<apex:actionFunction>` component also lets you call controller action methods through JavaScript.
- In general, `<apex:actionFunction>` is easier to use and requires less code, while JavaScript remoting offers more flexibility.

- Here are some specific differences between the two.
  The `<apex:actionFunction>` tag:

  - lets you specify rerender targets
  - submits the form
  - doesn’t require you to write any JavaScript

  JavaScript remoting:

  - lets you pass parameters
  - provides a callback
  - requires you to write some JavaScript

---

#### `<apex:actionSupport>`

##### 特点：

- AJAX request

- 向另一个组件添加 AJAX 支持的组件，允许服务器在发生特定事件（例如单击按钮或鼠标悬停）时异步刷新该组件。

- 可获取controller上sobject字段以外的input的值 （补充：只有`<apex:input>` `<apex:output>`能使用sobject项字段 ）

- DOM要素イベントに応じてコントローラーアクションをトリガーする。

- ```html
  <!--  Page: -->
  <apex:page controller="exampleCon">
      <apex:form>
          <apex:outputpanel id="counter">
              <apex:outputText value="Click Me!: {!count}"/>
              <apex:actionSupport event="onclick" 
                                  action="{!incrementCounter}" 
                                  rerender="counter" status="counterStatus"/>
          </apex:outputpanel>
          <apex:actionStatus id="counterStatus" 
                             startText=" (incrementing...)" 
                             stopText=" (done)"/>
      </apex:form>
  </apex:page>	
  
  /***  Controller: ***/
  public class exampleCon {
      Integer count = 0;                    
      public PageReference incrementCounter() {
              count++;
              return null;
      }                   
      public Integer getCount() {
          return count;
      }
  }
  ```

  

---

#### ```<apex:pageMessage>```

##### 特点：

- 显示严重性的错误、警告和其他类型的消息

- 用 Salesforce 样式呈现

- ```html
  <apex:pageMessage summary="This pageMessage will always display. Validation error 
             messages appear in the pageMessages component." severity="warning" strength="3" />
  <apex:pageMessages />
  ```

  

#### ```<apex:pageMessages>```

##### 特点：

- 显示为当前页面上的所有组件生成的所有消息

- 用 Salesforce 样式呈现

- ApexPages.addMessages(ex);

- ```html
  <apex:pageMessages />
  ```


#### `<apex:messages>`

特点：

- 为当前页面上的所有组件生成的所有消息
- 如果组件不包含在页面中，大多数警告和错误消息仅显示在调试日志中。
- ApexPages.addMessages(ex);
- newAccount.Name.addMessage();

#### `<apex:message>`

特点：

- 

---

#### `<apex:actionPoller>`

- 根据您指定的时间间隔向服务器发送 AJAX 请求的计时器。
- 每个请求都可能导致完整或部分页面更新。
- 一个 <apex:actionPoller >必须在其作用的区域内。例如，要使用一个<apex:actionPoller > 与 <apex:actionRegion >， 这 <apex:actionPoller > 必须在 <apex:actionRegion >.

**使用时的注意事项 <apex:actionPoller >**

- 使用的操作方法 <apex:actionPoller >应该是轻量级的。最好的做法是避免在调用的操作方法中执行 DML、外部服务调用和其他资源密集型操作。<apex:actionPoller >. 仔细考虑您的操作方法被重复调用的效果<apex:actionPoller > 在您指定的时间间隔内，特别是如果它用于将广泛分布的页面或长时间打开的页面。
- <apex:actionPoller >定期刷新连接，使登录会话保持活动状态。一个页面<apex:actionPoller > 它不会因为不活动而超时。
- 如果 <apex:actionPoller > 曾经作为另一个动作的结果重新渲染，它会重置自己。
- 避免将此组件与增强列表一起使用。

```html
<!--  Page -->		
<apex:page controller="exampleCon">
    <apex:form>
        <apex:outputText value="Watch this counter: {!count}" id="counter"/>
        <apex:actionPoller action="{!incrementCounter}" reRender="counter" interval="15"/>
    </apex:form>
</apex:page>
	
/***  Controller: ***/		
public class exampleCon {
    Integer count = 0;	
    public PageReference incrementCounter() {
        count++;
        return null;
    }		
    public Integer getCount() {
        return count;
    }
}
```

---

#### `<apex:actionRegion>`

- 组件内的AJAX可后台交互。

- ajax返回结果想反应到画面是 请使用以下组件的`rerender `属性

  - ` <apex:actionSupport>` 
  - ` <apex:actionPoller>` 
  - ` <apex:commandButton>,` 
  - `<apex:commandLink>`
  - `<apex:tab>`
  - `<apex:tabPanel>`

- ```html
        <apex:actionRegion>
          <apex:inputField value="{!opportunity.stageName}" id="stage">
            <apex:actionSupport event="onchange" rerender="thePageBlock"
                                status="status"/>
            </apex:inputField>
         </apex:actionRegion>
  ```


---

#### `<flow:interview>`

VF引入Flow组件

```HTML
<!-- Page: -->
<apex:page controller="exampleCon">
<!-- embed a simple flow -->
	<flow:interview name="my_flow" interview="{!my_interview}"></flow:interview>
	<!-- get a variable from the embedded flow using my_interview.my_variable -->
	<apex:outputText value="here is my_variable : {!my_interview.my_variable}"/>
</apex:page>

/*** Controller ***/
public class exampleCon {
    Flow.Interview.my_flow my_interview {get; set;}
}
```

---

#### `<apex:includeScript>`

```html
<apex:includeScript value="{!$Resource.example_js}"/>
// 上面的示例呈现以下 HTML：
<script type='text/javascript' src='/resource/1233160164000/example_js'>
```

---

#### `$<apex:stylesheet>`

```html
// 引入样式
<apex:stylesheet value="/resources/htdocs/css/basic.css"/>
```



---

#### RemoteAction Annotation

```java
[namespace.]MyController.method(
    [parameters...,]
    callbackFunction,
    [configuration]
);
//---------
@RemoteAction
global static String getItemId(String objectName) { ... }
```

- @RemoteAction
- static
- global or public

---

#### `<apex:include>`

将第二个 Visualforce 页面插入当前页面的组件。

```html
<!-- Page: -->
<apex:page id="thePage">
	<apex:outputText value="(page) This is the page."/><br/>
	<apex:include pageName="include"/>
</apex:page>
			
<!-- Page: include -->
<apex:page id="theIncludedPage">
	<apex:outputText value="(include) This is text from another page."/>
</apex:page>
```

---

#### `<apex:composition>`

引入模板。

可以传值到模板

```html
<!-- Page: composition -->
<!-- This page acts as the template. Create it first, then the page below.  -->	
<apex:page>
	<apex:outputText value="(template) This is before the header"/><br/>
	<apex:insert name="header"/><br/>
	<apex:outputText value="(template) This is between the header and body"/><br/>
	<apex:insert name="body"/>
</apex:page>
			
<!-- Page: page -->
<apex:page>
	<apex:composition template="composition">
		<apex:define name="header">(page) This is the header of mypage</apex:define>
		<apex:define name="body">(page) This is the body of mypage</apex:define>
	</apex:composition>
</apex:page><!-- Page: -->
<apex:page id="thePage">
	<apex:outputText value="(page) This is the page."/><br/>
	<apex:include pageName="include"/>
</apex:page>
			
<!-- Page: include -->
<apex:page id="theIncludedPage">
	<apex:outputText value="(include) This is text from another page."/>
</apex:page>

// 上面的示例呈现以下 HTML：
(template) This is before the header<br/>
(page) This is the header of mypage<br/>
(template) This is between the header and body<br/>
(page) This is the body of mypage
```

---

#### `<apex:component>`

自定义 Visualforce 组件。

```html
<!-- Page: -->
<apex:page>
    <c:myComponent myValue="My component's value" borderColor="red" />
</apex:page>
<!-- Component:myComponent -->
<apex:component>
    <apex:attribute name="myValue" description="This is the value for the component."
        type="String" required="true"/>
    <apex:attribute name="borderColor" description="This is color for the border."
        type="String" required="true"/>
    <h1 style="border:{!borderColor}">
        <apex:outputText value="{!myValue}"/>
    </h1>
</apex:component>
```

---

#### `<apex:outputLink>` 	

```html
<apex:outputLink value="https://www.salesforce.com" id="theLink">www.salesforce.com</apex:outputLink>
<apex:outputLink value="{!case.Id}" target="blank"> {!case.Name}</ apex:outputLink>
<apex:outputLink value="{!URLFOR($Action.Case.View.case.Id)}" target="blank">{!case.Name}</apex:outputLink>
```

---

#### `<apex:remoteObjects >`

```html
<apex:remoteObjects >
    <apex:remoteObjectModel name="Warehouse__c" jsShorthand="Warehouse" fields="Name,Id">
        <apex:remoteObjectField name="Phone__c" jsShorthand="Phone"/>
    </apex:remoteObjectModel>
</apex:remoteObjects>
```

##### Visualforce Remote Objects VS JavaScript Remoting

Visualforce Remote Objects:
	• Makes basic “CRUD” object access easy
	• Doesn’t require any Apex code
	• Supports minimal server-side application logic
	• Doesn’t provide automatic relationship traversals; you must look up related objects yourself
JavaScript Remoting:
	• Requires both JavaScript and Apex code
	• Supports complex server-side application logic
	• Handles complex object relationships better
	• Uses network connections (even) more efficiently

---

#### `<apex:commandLink>`

```html
<apex:commandLink action="{!save}" value="Save" id="theCommandLink"/>
```

action属性未指定时 点击只刷新画面

---

#### `<apex:dataTable>`

```html
<apex:page controller="dataTableCon" id="thePage">
    <apex:dataTable value="{!accounts}" var="account" id="theTable"
        rowClasses="odd,even" styleClass="tableClass">
        <apex:facet name="caption">table caption</apex:facet>
        <apex:facet name="header">table header</apex:facet>
        <apex:facet name="footer">table footer</apex:facet>

        <apex:column>
            <apex:facet name="header">Name</apex:facet>
            <apex:facet name="footer">column footer</apex:facet>
            <apex:outputText value="{!account.name}"/>
        </apex:column>

        <apex:column>
            <apex:facet name="header">Owner</apex:facet>
            <apex:facet name="footer">column footer</apex:facet>
            <apex:outputText value="{!account.owner.name}"/>
        </apex:column>

    </apex:dataTable>
</apex:page>
```

---

```javascript
Visualforce.remoting.Manager.invokeAction(
	'{!$RemoteAction.XXXController.methodName}',
  param,
  callbackfunction(){}
)
```

---

https://developer.salesforce.com/docs/atlas.en-us.224.0.pages.meta/pages/pages_variables.htm?_ga=2.181079535.912731606.1660867239-151797989.1660867239

## 全局变量

表达式 {! $GlobalName.fieldName }

[全局变量](https://developer.salesforce.com/docs/atlas.en-us.224.0.pages.meta/pages/pages_variables_global.htm?_ga=2.66938214.912731606.1660867239-151797989.1660867239)

- $User
- $Label
- $Organization
- $Setup
- $Page
- 等等。。。

---

## 公式表达式

- `&`字符是连接字符串 

  - {! $User.FirstName & ' ' & $User.LastName }

- 日期计算

  - ```html
    <p> Today's Date is {! TODAY() } </p>
    <p> Next week it will be {! TODAY() + 7 } </p>
    
    <p>The year today is {! YEAR(TODAY()) }</p>
    <p>Tomorrow will be day number  {! DAY(TODAY() + 1) }</p>
    <p>Let's find a maximum: {! MAX(1,2,3,4,5,6,5,4,3,2,1) } </p>
    <p>The square root of 49 is {! SQRT(49) }</p>
    <p>Is it true?  {! CONTAINS('salesforce.com', 'force.com') }</p>
    ```

- 条件表达式

  - ```html
    <p>{! IF( CONTAINS('salesforce.com','force.com'),'Yep', 'Nope') }</p>
    <p>{! IF( DAY(TODAY()) < 15,'Before the 15th', 'The 15th or after') }</p>
    ```

- 循环

  - ```html
    <apex:repeat value="{!contacts}" var="c">
        <div>{!c.Title}</div>
    </apex:repeat>
    ```



---

### 使用静态资源

```
<apex:includeScript value="{! $Resource.jQuery }">
<apex:stylesheet>
<apex:image>
```



```html
<apex:page showHeader="false" sidebar="false" standardStylesheets="false">
    <!-- Add static resources to page's <head> -->
    <apex:stylesheet value="{!
        URLFOR($Resource.jQueryMobile,'jquery/jquery.mobile-1.4.5.css')}"/>
    <apex:includeScript value="{! $Resource.jQueryMobile }"/>
    <apex:includeScript value="{!
        URLFOR($Resource.jQueryMobile,'jquery/jquery.mobile-1.4.5.js')}"/>
    <div style="margin-left: auto; margin-right: auto; width: 50%">
        <!-- Display images directly referenced in a static resource -->
        <h3>Images</h3>
        <p>A hidden message:
            <apex:image alt="eye" title="eye"
                url="{!URLFOR($Resource.jQueryMobile, 'jquery/images/icons-png/eye-black.png')}"/>
            <apex:image alt="heart" title="heart"
                url="{!URLFOR($Resource.jQueryMobile, 'jquery/images/icons-png/heart-black.png')}"/>
            <apex:image alt="cloud" title="cloud"
                url="{!URLFOR($Resource.jQueryMobile, 'jquery/images/icons-png/cloud-black.png')}"/>
        </p>
    <!-- Display images referenced by CSS styles, all from a static resource. -->
    <h3>Background Images on Buttons</h3>
    <button class="ui-btn ui-shadow ui-corner-all 
        ui-btn-icon-left ui-icon-action">action</button>
    <button class="ui-btn ui-shadow ui-corner-all 
        ui-btn-icon-left ui-icon-star">star</button>
    </div>
</apex:page>
```



