#### SOAP Callouts

[开发文档](https://developer.salesforce.com/docs/atlas.en-us.224.0.apexcode.meta/apexcode/apex_callouts_wsdl2apex_testing.htm)

[trailhead](https://trailhead.salesforce.com/en/content/learn/modules/apex_integration_services/apex_integration_soap_callouts)

SF 发起沟通外部系统

也就可以叫做Web Service

操作：

- 根据WSDL生成Apex类
- Remote Site Settings来授权远程站点

测试：

- WebServiceMock
  - ```global/public class WebServiceMockImpl implements WebServiceMock```
  - ```global/public void doInvoke(...){}```
  - @isTest => 6 MB limit
- WebSvcCallout 执行类
- WebSvcCalloutTest 测试执行类
  - Fake response   ```Test.setMock(WebServiceMock.class, new WebServiceMock());```
  - Call the method
  - Verify that a fake result is returned

-----

#### Restful Callouts

测试

```javascript
@isTest
global class AnimalsHttpCalloutMock implements HttpCalloutMock {
    // Implement this interface method
    global HTTPResponse respond(HTTPRequest request) {
        // Create a fake response
        HttpResponse response = new HttpResponse();
        response.setHeader('Content-Type', 'application/json');
        response.setBody('{"animals": ["majestic badger", "fluffy bunny", "scary bear", "chicken", "mighty moose"]}');
        response.setStatusCode(200);
        return response; 
    }
}
```



---

#### Apex Web Service

##### 将类公开为 REST Service,允许外部系统进来访问

特点

- @RestResource(urlMapping='/Account/*')
- global static method

Supported Data Types for Apex REST

- Apex primitives (excluding Object and Blob).
- sObjects
- Lists of Apex primitives or sObjects (only maps with String keys are supported).
- maps with String keys are supported
- User-defined types that contain member variables of the types listed above.

```java
// https://yourInstance.my.salesforce.com/services/apexrest/Account/*。
@RestResource(urlMapping='/Account/*')
global with sharing class MyRestResource {
    @HttpGet
    global static Account getRecord() {
        // Add your code
    }
}
```

| 注解          | 行动     | 细节                             |
| :------------ | :------- | :------------------------------- |
| `@HttpGet`    | 读       | 读取或检索记录。                 |
| `@HttpPost`   | 创建     | 创建记录。                       |
| `@HttpDelete` | 删除     | 删除记录。                       |
| `@HttpPut`    | 向上插入 | 通常用于更新现有记录或创建记录。 |
| `@HttpPatch`  | 更新     | 通常用于更新现有记录中的字段。   |

测试：

- RestRequest request = new RestRequest(); 来mock requets

##### 将类公开为 SOAP Service

特点

- global class
- webservice static method

```java
global with sharing class MySOAPWebService {
    webservice static Account getRecord(String id) {
        // Add your code
    }
}
```

---

### Webservice注意事项

- 不可为内部类
- 不能定义为interface
- 枚举不能在 Web 服务方法中使用
- 不能在trigger调用webservice
- global class
- global static method
- 返回值不能是以下类型
  - Maps
  - Sets
  - Pattern objects
  - Matcher objects
  - Exception objects
- すべてのクラスで使用可能
- 含まれるメンバー変数に使用
- Webサービスメソッドは、管理パッケージコードでは非推奨にできません
- Webサービスのメソッドは、カスタムApexクラスをパラメーターデータ型として公開できます。
- Webサービスメソッドは、グローバルとして宣言されているApexクラスにのみ追加できま
