# API介绍

#### SOAP API

特征：

- 通过WSDL定义参数
- 仅支持 XML
- 大多数 SOAP API 功能也可通过 REST API 获得

- Account、Lead、CustomObject等的CURD操作
- パスワードの維持、検索の実行などを可能にします

---

#### REST API

特征：

- 基于 RESTful,通过 REST 资源和 HTTP 方法公开各种 Salesforce 功能
- 支持XML 和 JSON
- CRUD记录
- 查询对象元数据
- 查询Limit信息
- 优点包括易于集成和开发，并且是用于移动应用程序和 Web 项目的绝佳技术选择

---

#### Bulk API

特征：

- 一种专门处理大量数据的 RESTful API
- Asynchronous

---

#### Streaming API

特征：

- 数据进行更改时触发的通知
- Bayeux（REST，SOAP (WSDL)之外的一种）
- JSON
- Asynchronous
- publish-subscribe, or pub/sub模型
- pub/sub 减少了 API 请求的数量
- 发布事件消息 => 订阅者可以使用 CometD 接收通知
- 还可以使用 Apex 触发器或声明式地使用 Process Builder 和 Flow Builder 订阅某些类型的事件

---

#### Metadata API

特征：

- SOAP (WSDL)
- Asynchronous
- 组织检索、部署、创建、更新或删除自定义
- 沙箱或测试组织迁移到您的生产环境
-  基于Metadata API的工具
  - Salesforce Extensions for Visual Studio Code 
  - Ant 迁移工具（脚本或命令行在本地目录和 Salesforce 组织之间移动元数据）

---

#### API Access and Authentication

特征：

---

#### API Limits

特征：

---

#### Tooling API

特征：

- 构建自定义开发工具或应用程序

---

#### User Interface API

特征：

- 用于构建 Lightning Experience 和 Salesforce for Android、iOS 和移动 Web UI
- 让用户可以使用记录、列表视图、操作、收藏夹等
- 不必担心布局、选项列表、字段级安全性或共享

---

#### Apex REST API

特征：

- 将 Apex 方法公开为  Apex REST API
- 外部可通过 REST访问
- 支持 OAuth 2.0 和Session ID 进行授权

---

#### Apex SOAP API

特征：

- 将 Apex 方法公开为 SOAP Web
- 外部可通过 SOAP 访问
- 支持 OAuth 2.0 和Session ID 进行授权