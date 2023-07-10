### Component Configuration

- Lightning Tab

  ```html
  <aura:component implements="force:appHostable" >	
  </aura:component>
  ```

- Lightning Page

  ```html
  <aura:component implements="flexipage:availableForAllPageTypes" access="global">
  </aura:component>
  ```

- Lightning Record Page

  ```html
  <aura:component implements="flexipage:availableForRecordHome, force:hasRecordId" access="global">
  </aura:component>
  ```

  

- Experience Builder Site Page

  ```html
  <aura:component implements="forceCommunity:availableForAllPageTypes" access="global" >
  	
  </aura:component>

- Lightning Quick Action

  ```html
  <aura:component implements="force:lightningQuickAction,force:hasRecordId" >	
  </aura:component>
  ```

## 组件属性

[文档](https://developer.salesforce.com/docs/atlas.en-us.234.0.lightning.meta/lightning/components_attributes.htm)

| **属性名**  | **型**  | **説明**                                                     |
| :---------- | :------ | :----------------------------------------------------------- |
| access      | String  | 属性が独自の名前空間の外側で使用できるかどうかを示します。有効な値は、public (デフォルト)、global、private です。 |
| name        | String  | 必須。属性の名前。たとえば、aura:newCmp というコンポーネントで <aura:attribute name="isTrue" type="Boolean" /> を設定する場合は、<aura:newCmp isTrue="false" /> のようにコンポーネントをインスタンス化するときに、この属性を設定できます。 |
| type        | String  | 必須。属性の型。サポートされている基本のデータ型のリストについては、[「基本の型」](https://developer.salesforce.com/docs/atlas.ja-jp.234.0.lightning.meta/lightning/ref_attr_types_basic.htm)を参照してください。 |
| default     | String  | 属性のデフォルト値。必要に応じて上書きできます。デフォルト値を設定するときに、$Label、$Locale、および $Browser グローバル値プロバイダを使用する式を指定できます。または、init イベントを使用して動的なデフォルトを設定できます。[「コンポーネントの初期化時のアクションの呼び出し」](https://developer.salesforce.com/docs/atlas.ja-jp.234.0.lightning.meta/lightning/js_cb_init_handler.htm)を参照してください。 |
| required    | Boolean | 属性が必須かどうかを指定します。デフォルトは、false です。   |
| description | String  | 属性およびその用途の概要。                                   |

 - 基本类型

   - Boolean
   - Date
   - DateTime
   - Decimal (浮動小数点数計算の精度を保持するには、Double より Decimal のほうが適切です。これは通貨項目に適しています。)
   - Double
   - Integer
   - Long
   - String

   - String[]

     ```JAVA
     @AuraEnabled
     public static List<String> getStringArray() {
         String[] arrayItems = new String[]{ 'red', 'green', 'blue' };
         return arrayItems;
     }
     ```

- 函数类型
  - ```<aura:attribute name="callback" type="Function" />```
  
- 对象类型

  - ```<aura:attribute name="data" type="Object" />```
    - type="Map"代替type="Object" 避免服务器上的一些反序列化问题。
    - typeof 変数種別判断

- 标准和自定义对象类型

   ```html
    // 用户必须至少对属性类型中指定的对象具有读取权限。否则，组件不会加载。
    <aura:attribute name="acct" type="Account" />
    <aura:attribute name="expense" type="Expense__c" />```
   ```

    

- 集合

   ```html
   // type[] (Array)
   <aura:attribute name="colorPalette" type="String[]" default="['red', 'green']" />
   
   // List
   <aura:attribute name="colorPalette" type="List" default="['red', 'green']" />
   
   // Map
   <aura:attribute name="sectionLabels" type="Map" default="{ a: 'label1', b: 'label2' }" />
   
   // Set
   <aura:attribute name="collection" type="Set" default="['red', 'green', 'blue']" />
   ```

   ```javascript
   // Checking for Types
   // 	1 use typeof
   typeof component.get("v.myAttribute") === "string"
   // 	2 use a standard JavaScript method
   Array.isArray()
   
   // Setting List Items
   
   <aura:attribute name="numbers" type="List"/>
   <lightning:button onclick="{!c.getNumbers}" label="Display Numbers" />
     
   <aura:iteration var="num" items="{!v.numbers}">
     {!num.value}
   </aura:iteration>
   
   ({
     getNumbers: function(component, event, helper) {
       var numbers = [];
       for (var i = 0; i < 20; i++) {
         numbers.push({
           value: i
         });
       }
       component.set("v.numbers", numbers); 
       }
   })
   
   // Working with Map Items
   ({
       addToMap : function(cmp, event, helper) {
           var myMap = cmp.get("v.sectionLabels");
           myMap['c'] = 'label3';
           console.log("myMap: " + JSON.stringify(myMap));
           
           // get map entry
           var entryA = myMap['a'];
           console.log("entryA: " + entryA);
           
           // iterate map
           for (var key in myMap){
               console.log("key: " + key + ", value: " + myMap[key]);
           }
       }
   })
   ```

- 自定义 Apex 类类型

   ```html
   <aura:attribute name="color" type="docSampleNamespace.Color" />
   <aura:attribute name="colorPalette" type="docSampleNamespace.Color[]" />
   // 可以是自定义 Apex 类，以及以下标准 Apex 类
   list
   map
   
   // 只有public值用注解的实例属性和方法@AuraEnabled被序列化并返回。
   可以从以下 Apex 数据类型序列化@AuraEnabled属性和方法。
   - 除 BLOB 外的基本类型
   - Object
   - sObject
   - 集合类型（List 和 Map），当它们包含受支持类型的元素时
   ```

- 使用 Aura.Action 属性类型 (不推荐使用)

  例子：当您单击中的按钮时c:child， 这 父动作控制器中的动作c:parent被执行

  ```html
  <!-- child.cmp -->
  <aura:component>
      <aura:attribute name="onclick" type="Aura.Action"/>
  
      <p>Child component with Aura.Action attribute</p>
      <lightning:button label="Execute the passed action" onclick="{!v.onclick}"/>
  </aura:component>
  ```

  ```html
  <!-- parent.cmp -->
  <aura:component>
      <p>Parent component passes handler action to c:child</p>
      <c:child onclick="{!c.parentAction}"/>
  </aura:component>
  ```

## 表达式

- 输出表达式

  ```html
  {!v.desc}
  {!'Some text'}
  {!123}
  {!true}

-  条件表达式

  ```html
  <a class="{!v.location == '/active' ? 'selected' : ''}" href="#/active">Active</a>
  ```

  ```html
  <aura:attribute name="edit" type="Boolean" default="true"/>
  <aura:if isTrue="{!v.edit}">
      <lightning:button label="Edit"/>
      <aura:set attribute="else">
          You can’t edit this.
      </aura:set>
  </aura:if>
  ```

- 组件之间的数据绑定

  ```html
  <!--c:parent-->
  <aura:component>
      <aura:attribute name="parentAttr" type="String" default="parent attribute"/>
      
      <!-- Instantiate the child component -->
      <c:child childAttr="{!v.parentAttr}" />
  </aura:component>
  
  <c:child childAttr="{!v.parentAttr}" />
  <c:child childAttr="{#v.parentAttr}" />
  ```

  - {＃表达}（未绑定表达式）

    数据更新的行为与您在 JavaScript 中所期望的一样。原语，例如string, 是按值传递的，父子表达式的数据更新是解耦的。

    对象，例如大批或者地图, 是通过引用传递的，因此对子项中数据的更改会传播到父项。但是，不会通知父级中的更改处理程序。相同的行为适用于传播给子代的父代的更改。

  - {！表达}（绑定表达式）

    任一组件中的数据更新都通过两个组件中的双向数据绑定反映出来。同样，更改处理程序在父组件和子组件中都被触发。

- value providers

  $Browser

  ```javascript
  
  {!$Browser.isPhone}
  
  ({
      checkBrowser: function(component) {
          var device = $A.get("$Browser.formFactor");
          alert("You are using a " + device);
      }
  })
  ```

  $ContentAsset

  ```html
  <aura:component>
      <img src="{!$ContentAsset.websiteImages + 'pathinarchive=images/logo.jpg'}" alt="holiday wreath"/>
  </aura:component>
  
  
  <aura:component>
      <ltng:require styles="{!$ContentAsset.bookStyle}"/>
      <!-- "bookName" is defined in an asset file with DeveloperName of "bookStyle" -->
      <div id="bookTitle" class="bookName">
      </div>
  </aura:component>
  
  <aura:component>
      <ltng:require scripts="{!$ContentAsset.testDisplayData}"
  afterScriptsLoaded="{!c.displayData}"/>
  ...
  
      <aura:attribute name="TestData" type="String[]" ></aura:attribute>
          <div>
              <input type="text" id="sampleData" value ="{!v.TestData}" />
          </div>
  ...
  </aura:component>
  ```

  ```javascript
  ({
      displayData : function(component, event, helper) {
          var data = _datamap.getData();
          component.set("v.TestData", data);
      }
  })
  
  testDisplayData.js
  window._datamap = (function() {
      var data = ["Agree", "Disagree", "Strongly Agree", "Strongly Disagree", "Not Applicable"];
      return {
          getData: function() {
              return data.join(", ");
          }
      };
  }());
  ```

  $Locale

  ```html
  <aura:component>
      {!$Locale.language}
      {!$Locale.timezone}
      {!$Locale.numberFormat}
      {!$Locale.currencyFormat}
  </aura:component>
  ```

  ```java
  ({
      checkDevice: function(component) {
          var locale = $A.get("$Locale.language");
          alert("You are using " + locale);
      }
  })
  ```

  $Resource

  ```html
  <aura:component>
      <!-- Stand-alone static resources -->
      <img src="{!$Resource.generic_profile_svg}"/>
      <img src="{!$Resource.yourNamespace__generic_profile_svg}"/>
  
      <!-- Asset from an archive static resource -->
      <img src="{!$Resource.yourGraphics + '/images/logo.jpg'}"/>
      <img src="{!$Resource.yourNamespace__yourGraphics + '/images/logo.jpg'}"/>
  </aura:component>
  
  <aura:component>
    <ltng:require 
      styles="{!$Resource.jsLibraries  + '/styles/jsMyStyles.css'}"
      scripts="{!$Resource.jsLibraries + '/jsLibOne.js'}"
      afterScriptsLoaded="{!c.scriptsLoaded}" />
  </aura:component>
  
  // VF
  <apex:image url="{!$Resource.TestImage}" width="50" height="50"/>
  <apex:includeScript value="{!$Resource.MyJavascriptFile}"/>
  
  <apex:image url="{!URLFOR($Resource.TestZip,
                    'images/Bluehills.jpg')}" width="50" height="50"/>
  <apex:includeScript value="{!URLFOR($Resource.LibraryJS, '/base/subdir/file.js')}"/>
  
  // styles.css
  table { background-image: url('img/testimage.gif') }
  
  <apex:stylesheet value="{!URLFOR($Resource.style_resources, 'styles.css')}"/>
  ```

  ```javascript
  ({
      profileUrl: function(component) {
          var profUrl = $A.get('$Resource.yourGraphics') + '/images/avatar1.jpg';
          alert("Profile URL: " + profUrl);
      }
  })
  ```

  

## 初期化

```HTML
<aura:handler name="init" value="{!this}" action="{!c.doInit}"/>
({
    doInit : function(component, event, helper) {
        let mydate = component.get("v.expense.Date__c");
        if(mydate){
            component.set("v.formatdate", new Date(mydate));
        }
    },
})
```

## Event

```mermaid
A->B: Normal line
B-->C: Dashed line
C->>D: Open arrow
D-->>A: Dashed open arrow
```

