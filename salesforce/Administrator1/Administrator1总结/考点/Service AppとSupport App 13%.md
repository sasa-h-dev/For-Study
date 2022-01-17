### Service App と Support App `13%`

##### ケース管理の機能を説明する - ケースのプロセス - ケース設定 - ケースコメント

- Support Processes
- Support Settings
  - Default Case Owner

##### 与えられたシナリオに従って、ケース管理の自動化の方法を特定する

- ケースの割り当て（Lead Assignment Rules）
  - 把New Case根据设置的分配规则分配个指定User或Quene
  - 可选Email Template
- 自動レスポンス
  - 当New Lead创建后，根据设置的规则，发送邮件给指的地址
  - 可选Email Template
- エスカレーション
  - 指定条件的Case达到指定时间仍未解决，Auto-reassign到别的user或quene
- 来源
  - Web-to-ケース
  - メール-to ケース
  - Dataloader
  - ケースチーム
- Omni-Channel Settings
  - 定义的路由条件接收传入的工作项并将它们路由到最合格、可用的支持代理。

    - Queue-based routing
    - Skills-based routing
    - External routing

##### Salesforce ナレッジの機能を説明する

- 经验丰富的服务客服人员和内部作者会撰写文章
- 根据文章页面布局、用户Profile、操作和其他设置，控制信息发布或共享的位置及内容。

- 内部用户和客户可以快速找到并查看他们需要的文章。
- 客户包括
  - Customer Portal
  - Partner portal
  - Service Cloud Portal
  - Lightning Platform Sites
- Lightning 平台站点中启用 Salesforce Knowledge，则客户和合作伙伴将能够访问文章。
- 创建一个公用知识库，以便网站访问者能够查看文章。
- 特征：
  - Knowledge articles are always publicly available for customers.
  - Users can rate the helpfulness of articles.
- 用途：
  - To. display for customer self-service
  - To. resolve customer cases 
- 共享
  - 例如组织范围的默认值、所有者角色层次结构的访问以及基于标准的规则。

##### Experience Cloud サイトの機能を説明する

- 不论您称其入口网站、帮助论坛、支持社区、HR 中心，还是其他名称，都是Experience Cloud Site。
- 整合一切
- 利益相关者提供所需内容的简短列表
  - 为特定需求创造多种体验。
  - 将业务流程扩展到合作伙伴和客户。
  - 集成来自第三方提供商的数据（例如订单或财务信息）。
  - 使用主题和模板创建精美的品牌体验。
  - 使用 Salesforce CMS 创建内容并交付到任何渠道。

##### コミュニティの[使用例](https://help.salesforce.com/s/articleView?id=sf.users_license_types_customerportal_enterpriseadmin.htm&type=5)

- 従業員と流通業者、再販業者、納入業者を接続し、販売を促進する

- 顧客から回答を得られる一元的な場所を用意することにより、世界クラスのサービスを提供する

- ソーシャルな聴取、内容、取り組み、およびワークフローのすべてを一元管理する

- Customer Community  (Service cloud (customer) portal)

  - Customer can log, view, edit, and close their own cas
- knowledge
  - The Customer Community can be used with person accounts.
  - The portal can be customized with corporate branding.

- Customer Comunity Plus

  - 外部客户reports and dashboards用

- Partner Community

  ​	外部客户sales data用

- Channel Account
  - calculate their usage based on number of partners instead of number of individual users.

##### コミュニティエキスパートの指定

-  专家是意见社区的一个成员，代表贵组织发表可信和权威的论断。在专家发布评论或意见时，其名称 (![专家徽章](https://resources.help.salesforce.com/images/4b261fdf2ecd2df2ec3e3833bd95d5cc.png)) 旁边会显示一个独特图标。Salesforce 管理员可根据需要指定任意数量的专家。
- コミュニティエキスパートは、アイコンによって指定されることができる。
- コミュニティエキスパートは、Salesforceアイデアのために指定することができる。

