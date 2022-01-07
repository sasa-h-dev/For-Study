aura component

### `<aura:component>`

| 属性        | 类型      | 描述                                                         |
| :---------- | :-------- | :----------------------------------------------------------- |
| access      | String    | 指示组件是否可以在其自己的命名空间之外使用。可能的值是`public`（默认），和`global`。 |
| controller  | String    | 组件的服务器端控制器类的格式`namespace.myController`或`myController`如果使用默认命名空间。 |
| description | String    | 组件的描述。                                                 |
| extends     | Component | 要扩展的组件。                                               |
| extensible  | Boolean   | 设置为`true`是否可以扩展组件。默认为`false`。                |
| implements  | String    | 组件实现的接口的逗号分隔列表。                               |
| isTemplate  | Boolean   | 如果组件是模板，则设置为 true。默认为`false`。模板必须`isTemplate="true"`在其`aura:component`标签中设置。 |
| template    | Component | 此组件的模板。模板引导加载框架和应用程序。默认模板为`aura:template`。您可以通过创建自己的扩展默认模板的组件来自定义模板。有关更多信息，请参阅[Lightning 组件开发人员指南](https://developer.salesforce.com/docs/atlas.en-us.lightning.meta/lightning/apps_template_overview.htm)。 |

#### implements:

| Configuration                                                | Markup                                                       | Description                                                  |
| :----------------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| **Lightning Tab**                                            | implements="force:appHostable"                               | Creates a component for use as a navigation element in Lightning Experience or Salesforce mobile apps. |
| **Lightning Page**                                           | implements="flexipage:availableForAllPageTypes" and access="global" | Creates a component for use in Lightning pages or the Lightning App Builder. |
| **Lightning Record Page**                                    | implements="flexipage:availableForRecordHome, force:hasRecordId" and access="global" | Creates a component for use on a record home page in Lightning Experience. |
| **Experience Builder Site Page (previously Lightning Communities Page)** | implements="forceCommunity:availableForAllPageTypes" and access="global" | Creates a component that’s available for drag and drop in the Experience Builder. |
| **Lightning Quick Action**                                   | implements="force:lightningQuickAction"<br />implements="force:lightningQuickActionWithoutHeader<br />,force:hasRecordId" | Creates a component that can be used with a Lightning quick action. |
| **Lightning application bundle**                             |                                                              |                                                              |
| **Lightning Out Dependency App**                             | extends="ltng:outApp"                                        | Creates an empty Lightning Out dependency app.               |

##### force

| Markup                                  | Description                                                  |
| :-------------------------------------- | :----------------------------------------------------------- |
| force:appHostable                       | 自定义选项卡                                                 |
| force:hasRecordId                       | <aura:attribute name="recordId" type="String" />             |
| force:hasSObjectName                    | <aura:attribute name="sObjectName" type="String" />          |
| force:lightningQuickAction              | 实现`force:lightningQuickAction`界面的组件显示在带有标准动作控件（例如取消按钮）的面板中。这些组件可以在面板主体中显示和实现自己的控件，但不能影响标准控件。 |
| force:lightningQuickActionWithoutHeader | 界面无额外的控件                                             |

---

### `<design:component>`

```html
<design:component label="Hello World">
    <design:attribute name="subject" label="Subject" description="Name of the person you want to greet" />
    <design:attribute name="greeting" label="Greeting" />
    <design:supportedFormFactors>
        <design:supportedFormFactor type="Large"/>
        <design:supportedFormFactor type="Small"/>
    </design:supportedFormFactors>
    <sfdc:objects>
        <sfdc:object>Custom__c</sfdc:object>
        <sfdc:object>Opportunity</sfdc:object>
    </sfdc:objects>
</design:component>
```

