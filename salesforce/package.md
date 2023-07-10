### AppExchange Managed and Unmanaged Packages

| Attribute     | Managed Packages                                             | Unmanaged Packages                                           |
| ------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Customization | You can’t view or change the solution’s code or metadata.    | You can customize code and metadata, if desired.             |
| Upgrades      | The provider can automatically upgrade the solution.         | To receive an upgrade, you must uninstall the package from your org and then reinstall a new version from AppExchange. |
| Org limits    | The contents of the package don’t count against the app, tab, and object limits in your org | The contents of the package count against the app, tab, and object limits in your org. |



包是一个发布工件，它是一组相关的代码和自定义项。

包可以是围绕从 AppExchange 安装的受管包构建的扩展

解锁包，特别适用于内部业务应用程序。

VCS 来管理和版本化您的源代码

如果您是 Salesforce 客户、承包商、顾问或系统集成商，那么解锁包非常适合您！

解锁包提供了一个可重复、可编写脚本和可跟踪的工具，用于在您的组织中引入和管理变更。

包将成为您用于组织元数据的容器。

包也成为您在环境之间迁移元数据的方式。

采用包装将影响您管理和思考 Salesforce 组织结构的方式。

使用解锁包，您有很大的灵活性。您的管理员可以直接在生产中进行更改以响应紧急更改请求，因为解锁包中的元数据可以在生产组织中进行修改。

解锁的包由开发人员控制。任何新软件包版本的安装都会覆盖直接在生产组织中所做的更改。管理员必须将生产组织中所做的任何更改直接传达给开发团队，以便适当地更新包，这一点至关重要。

修改元数据→创建包版本→测试包版本→部署到生产

```shell
sfdx version
sfdx update
打开Dev Hub
单击启用开发中心。同时选择Enable Unlocked Packages和Second-Generation Managed Packages。
sfdx auth:web:login -d -a DevHub
// 创建一个新项目
cd Documents
sfdx force:project:create -n PackageXMLProject
cd PackageXMLProject

// 创建临时组织
sfdx force:org:create -f config/project-scratch-def.json -s
sfdx force:source:push
sfdx force:source:pull

// 要查看您的组织限制，请运行以下命令：
sfdx force:limits:api:display -u DevHub

// 部署
sfdx force:source:deploy -x ./package.xml -u DevHub -w10
```

```
创建包
sfdx force:package:create --name dreamhouse --description "My Package" --packagetype Unlocked --path force-app --nonamespace --targetdevhubusername DevHub
--name 是包名。此名称是您在运行后续打包命令时可以使用的别名。
--path 是包含包内容的目录。
--packagetype 指示您正在创建的包类型，在这种情况下，未锁定。

sfdx force:package:list.

创建一个 Scratch 组织来测试包
sfdx force:org:create --definitionfile config/project-scratch-def.json --durationdays 30 --setalias MyScratchOrg -v DevHub

sfdx force:package:version:create -p dreamhouse -d force-app -k test1234 --wait 10 -v DevHub
-p 是映射到包 ID 的包别名。
-d 是包含包内容的目录。
-k 是安装密钥，可保护您的软件包不被未经授权的个人安装。

安装包
sfdx force:package:install --wait 10 --publishwait 10 --package dreamhouse@1.0.0-1 -k test1234 -r -u MyScratchOrg 

sfdx force:org:open -u MyScratchOrg

发布包版本
sfdx force:package:version:promote -p dreamhouse@1.0.0-1 -v DevHub
```

