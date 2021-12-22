# lwc知识点

### Event

![event flow](https://camo.qiitausercontent.com/bac75541d7d71400b74a5f3cebe4acdf6f0fb07a/68747470733a2f2f71696974612d696d6167652d73746f72652e73332e61702d6e6f727468656173742d312e616d617a6f6e6177732e636f6d2f302f3132353632312f33666436626162382d396464612d613034652d646239312d3937316138363435643636352e706e67)

```javascript
// 子组件
btnClick() {
    const event = new CustomEvent('tileclick', {
        // detail contains only primitives
         detail: this.product.fields.Id.value
    });
    // Fire the event from c-tile
    this.dispatchEvent(event);
}

// 父组件
// html
<c-tile
  key={bike.fields.Id.value}
  product={bike}
  ontileclick={handleTileClick}>
</c-tile>
// js
handleTileClick() {
   this.color = event.detail.value;
}
```

---

### Decorators

- @api
- @track
- @wire

---

### @salesforce Modules

- @salesforce/apex

  - ```javascript
    import { LightningElement, api, wire } from 'lwc';
    import getRelatedContacts from '@salesforce/apex/AccountController.getRelatedContacts';
    export default class WireApexProperty extends LightningElement {
        @api recordId;
        @wire(getRelatedContacts, { accountId: '$recordId' })
        contacts;
      	get errors() {
            return (this.contacts.error) ?
                reduceErrors(this.contacts.error) : [];
        }
    }
    ```

  - ```javascript
    import { LightningElement, api, wire } from 'lwc';
    import getRelatedContacts from '@salesforce/apex/AccountController.getRelatedContacts';
    export default class CallApexImperative extends LightningElement {
        @api recordId;
        handleButtonClick() {
            getRelatedContacts({ //imperative Apex call
                accountId: this.recordId
            })
                .then(contacts => {
                    //code to execute if related contacts are returned successfully
                })
                .catch(error => {
                    //code to execute if related contacts are not returned successfully
                });
        }
    }
    ```

    

- @salesforce/schema

  - import ACCOUNT_NAME_FIELD from '@salesforce/schema/Account.Name';

- @salesforce/apexContinuation

- @salesforce/client/formFactor

- @salesforce/community

- @salesforce/contentAssetUrl

- @salesforce/i18n

- @salesforce/label

- @salesforce/messageChannel

- @salesforce/resourceUrl

- @salesforce/user

- @salesforce/userPermission

- @salesforce/customPermission

---

### `lightning/ui*Api` Wire Adapters and Functions

- **[lightning/uiRecordApi](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/reference_lightning_ui_api_record.html)** ※
  This module includes wire adapters to record data and get default values to create records. It also includes JavaScript APIs to create, delete, update, and refresh records.

  - ```javascript
    import { getRecord } from 'lightning/uiRecordApi';
    // 修饰属性
    @wire(getRecord, { recordId: '$recordId', fields: [ACCOUNT_NAME_FIELD] })
    account;
    
    // 修饰方法
    @wire(getRecord, { recordId: '$recordId', fields: [ACCOUNT_NAME_FIELD] })
    wiredAccount({data, error}) {
        console.log('Execute logic each time a new value is provisioned');
        if (data) {
            this.data = data;
            this.error = undefined;
        } else if (error) {
            this.error = error;
            this.data = undefined;
        }
    }
    ```

  - ```javascript
    import { createRecord } from 'lightning/uiRecordApi';
    handleButtonClick() {
        const recordInput = {
            apiName: ACCOUNT_OBJECT.objectApiName,
            fields: {
                [ACCOUNT_NAME_FIELD.fieldApiName] : 'ACME'
            }
        };
        createRecord(recordInput)
            .then(account => {
                // code to execute if create operation is successful
            })
            .catch(error => {
                // code to execute if create operation is not successful
            });
    }
    ```

    

- **[Salesforce Objects Supported by lightning/ui\*Api Modules](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/reference_supported_objects.html)**
  The wire adapters and JavaScript functions in `lightning/ui*Api` modules are built on User Interface API. User Interface API supports all custom objects and many standard objects.

- **[lightning/uiAppsApi (Beta)](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/reference_lightning_ui_api_apps.html)**
  Get data and metadata for apps displayed in the Salesforce UI.

- **[lightning/uiListsApi](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/reference_lightning_ui_api_lists_ui.html)**
  Get the metadata for a list view.

- **[lightning/uiListApi (Deprecated)](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/reference_lightning_ui_api_list_ui.html)**
  Get the records and metadata for a list view.

- **[lightning/uiObjectInfoApi](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/reference_lightning_ui_api_object_info.html)**
  Get object metadata, and get picklist values.

  
