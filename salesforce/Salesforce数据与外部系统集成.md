# Salesforce 数据与外部系统集成

https://trailhead.salesforce.com/content/learn/modules/change-data-capture/test-the-change-event-trigger

### 方式

- 执行定期导出或 API 轮询
  - バッチ
  - 外部系统访问Salesforce API进行查询，然后同步到外部系统
- 使用更改数据捕获来更新外部系统中的数据
  - 数据复制包括以下阶段
    - 整个数据集的初始（第 0 天）副本到外部系统
    - 将新数据和更新数据持续同步到外部系统
    - 协调两个系统之间的重复数据
  - Streaming Events
    - publisher/subscriber model and push technology
    - Notification messages are sent to the event bus to which clients can subscribe through a channel
    - Event-driven systems streamline the communication between distributed enterprise systems, increase scalability, and deliver real-time data. 
- 