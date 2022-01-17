### SObject `14%`

##### 標準オブジェクトのアーキテクチャとリレーションモデルを説明する

- 对象关系概览
  - 主従関係
  - 参照関係
  - 外部参照
  - 多対多
  - 間接参照
  - 階層

- 常见的表关系

  ```mermaid
  erDiagram
      Account ||--o{ Lead : loopup
      Account ||--o{ Opportunity : loopup
      Account ||--o{ Contact : loopup
  		Account ||--o{ Case : loopup
  		Contact ||--o{ Case : loopup
  ```

  

##### カスタムオブジェクトと標準オブジェクトで、項目、ページレイアウトを作成、削除、カスタマイズする方法や、項目を削除した場合の影響を説明する

- 标准SObject及其字段不能被删除

- 标准表字段只能修改
  - lable
  - help text
  - 变更picklist列表选项
  
- RecordType (重点 业务上经常用来区分 不同的业务流程)
  - 重要的 创建RecordType后，需要在Profile里赋予权限。
  - 不同的RecordType，可以控制picklist有不同的选项值
  - 不同的RecordType，可以分配给不同的Page layout，也可分给相同Page layout
  - 商談、ケース、リード、ソリューションの場合、ビジネスプロセスの設定が必要
  
- Page layout，RecordType，Profile的关系
  - 不同的RecordType可以显示不同的Page layout
  - 不同的Profile可以显示不同的Page layout
  
- 選択リストを連動させる
  - 制御項目：都道府県⇒東京都 
  - 連動項目：区域：北区、渋谷区など
  - 補足説明　制御項目一つに対したくさんの連動項目を持つことができる
  
- 删除字段 （考点 送分题）
  - 删除自定义字段时，将删除所有的字段历史数据并且不再跟踪更改
  - 删除后该字段及值可复活(在 15 天之后自动将其永久删除)
  - workflow，rule，apex中被使用的话，则无法删除
  - 无法删除在公式中引用的字段
  - page layout中的自动被删除，无需手动删除（但可能会影响页面布局）
  - 后台运行中如果正在使用，则无法删除例如（更新累计汇总字段） 可稍后重试
  
- 可以总做外部ID字段类型
  - テキスト項目
  - 数値項目
  - メールアドレス項目
  
- 数式字段
  - 根据数式自动设值，只能参照，不可编辑
  - 无法删除在公式中引用的字段
  - 字段的值不能被引用到其他公式
  
- Validation Rules
  - Error Condition 
  - Error Message
  - 注意执行顺序，Workflow更新字段时，不会再次触发Validation Rules
    1. 入力規則
    2. 割り当てルール
    3. 自動レスポンスルール
    4. ワークフロールール
    5. プロセスビルダー
    6. エスカレーションルール
  
- Field History Tracking
  - up to 18 months through your org
  - up to 24 months via the API
  - StandardObjectName`History` or *CustomObjectName*__`History`
  - 对象
    - custom objects 
    - 大部分standard objects.
  
- 标准表(特别点)

  是：

  - レポート
  - ダッシュボード

  不是

  - サポート
  - マーケティング
  - サービスアドレス

##### 与えられたシナリオに従って、カスタムオブジェクトと標準オブジェクトのページレイアウト、レコードタイプおよびビジネスプロセスを判断する

- Business Processes
  - Lead Processes (Lead RecordType)
  - Sales Processes (Opportunity RecordType)
  - Support Process (Case RecordType)
- Opportunity(Lead,Case)中的Stages字段定义了整个业务流程，但是不同的产品很可能对应不同的业务流程。Business Processes就是定义了不同业务流程
- Opportunity，Lead，Case中创建RecortType的时候必须指定Business Processes（需事先定义）
- 当业务流程相同时，只想要页面的某个picklist选项值不同时，需创建俩个RecordType指定同一个Business Processes，在根据RecordType控制选项值既可
- 边做题边理解，Trailhead也有教程，可跟做。

