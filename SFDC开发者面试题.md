### 初级开发者

**1.介绍一下SFDC Sandbox**

| 種別          | Matadate Copy | Data Cope | 更新間隔 | データストレージ制限        |
| ------------- | ------------- | --------- | -------- | --------------------------- |
| Developer     | YES           | NO        | 1 日     | 200MB                       |
| Developer Pro | YES           | NO        | 1 日     | 1GB                         |
| Partial Copy  | YES           | 一部      | 5 日     | 5GB                         |
| Full          | YES           | YES       | 29 日    | 本番環境と同様 (コピー時点) |

**2.Salesforce 介绍数据权限部分（包括sObject,Filed,Record）** 

1. 組織レベル

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

**3.对比一下workflow  VS process builder**

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



**4.Apex获取RecordType相关情报**

```
// 1.从RecordType Object中获取
List<RecordType> rt = [SELECT Id,Name FROM RecordType WHERE SobjectType='Son__c'];

// 2.从Schema.DescribeSObjectResult中获取
Schema.DescribeSObjectResult d = Schema.SObjectType.Son__c;
```



### 高级开发者

**1.你对VisualForce Page, aura, lwc了解多少**，实际开发用过哪个

2.你知道的Salesforce中 异步请求有哪些，简单介绍一下

| Type           | Overview                                                 | Common Scenarios    |
| :------------- | :------------------------------------------------------- | :------------------ |
| Future Methods | 另外启动线程 在程序空闲是执行 （执行顺序无法保障）       | Web service callout |
| Batch Apex     | 处理超出制限的大量数据                                   | 数据清理或记录归档  |
| Queueable Apex | 类似@future,但可按指定顺序执行，且可用相对复杂的数据类型 | 按顺序访问外部 Web  |
| Scheduled Apex | 在指定时间执行                                           | 每日或每周任务      |

3.你用过哪些Salesforce API

- RustAPI, Soap API，MateData API ，Bulk API ... 