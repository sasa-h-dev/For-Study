# aura知识点

### 语法

```html
// 属性
<aura:attribute name="messages" type="List"
        default="['You look nice today.',
            'Great weather we\'re having.']"/>
 <aura:attribute name="newExpense" type="Expense__c"
         default="{ 'sobjectType': 'Expense__c','Reimbursed__c': false }"/>
// 循环
<aura:iteration items="{!v.messages}" var="msg">
    <p><c:helloMessage message="{!msg}"/></p>
</aura:iteration>
// 判断
<aura:if isTrue="{!$Browser.isIPhone}">
    <p><c:helloMessage message="{!v.messages[0]}"/></p>
<aura:set attribute="else">
    <p><c:helloMessage message="{!v.messages[1]}"/></p>
    </aura:set>
</aura:if>

// 页面读取页面的属性{!v.属性名}
{!
firstName}
// 页面调用js的方法{!c.方法名}
{!c.getFirstName}
```

```javascript
// js取画面的属性值
var theLabel = cmp.get("v.label");
// js设置画面的属性值
component.set("v.message", theLabel); 
// 通过aura:id 获取页面元素 返回数组 
component.find(theId);
```

