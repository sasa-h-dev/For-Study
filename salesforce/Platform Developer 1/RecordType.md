### RecordType

#### 用途

RecordType可为不同的用户提供

- 不同的业务流程

- 不同的选项列表值

- 不同的页面布局 (不同RecordType可看到不同page layout,不同Profile也可看到不同page layout)

  

#### Apex获取RecordType相关情报

```java
// 1.从RecordType Object中获取
List<RecordType> rt = [SELECT Id,Name FROM RecordType WHERE SobjectType='Son__c'];
system.debug(rt);
//   (RecordType:{Id=0120o000001ZNawAAG, Name=NorthEastType}, 
//   RecordType:{Id=0120o000001ZNbBAAW, Name=NorthWestType})
```

```java
// 2.从Schema.DescribeSObjectResult中获取
Schema.DescribeSObjectResult d = Schema.SObjectType.Son__c;

//   getRecordTypeInfosById
Map<Id,Schema.RecordTypeInfo> rtMapById = d.getRecordTypeInfosById();
Schema.RecordTypeInfo rtById =  rtMapById.get('0120o000001ZNawAAG');
system.debug(rtById);
//Schema.RecordTypeInfo[getDeveloperName=NorthEastType;getName=NorthEastType;getRecordTypeId=0120o000001ZNawAAG;isActive=true;isAvailable=true;isDefaultRecordTypeMapping=true;isMaster=false;]

//   getRecordTypeInfosByName
Map<String,Schema.RecordTypeInfo> rtMapByName = d.getRecordTypeInfosByName();
Schema.RecordTypeInfo rtByName =  rtMapByName.get('NorthEastType');
system.debug(rtByName);
//Schema.RecordTypeInfo[getDeveloperName=NorthEastType;getName=NorthEastType;getRecordTypeId=0120o000001ZNawAAG;isActive=true;isAvailable=true;isDefaultRecordTypeMapping=true;isMaster=false;]
```

