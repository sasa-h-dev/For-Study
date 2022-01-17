### Sharing Settings

##### Organization-Wide Defaults

- User对自己所拥有的Record以为的Record的权限

- 基于SObject级别设定

- 权限种类

  - Private
  - Public Read Only
  - Public Read/Write

- がある。他には親レコードやキャンペーンに連動、公開/参照・更新・所有権の移行など。レコードの詳細画面で共有ボタンが表示されないのは公開/参照もしくは公開/参照・更新可能になっている為である。

  ---

##### Role Sharing

- ロールの上位ユーザは下位ユーザのレコードを参照することができる。
  →上司は部下のレコードをみれるが逆はできない。

- フルアクセス権まで継承可能である。

  ---

##### Sharing Rules

組織の共有設定の例外。

何を、誰に、どのレベルで共有するかの条件を決めて、それに合致したレコードを共有する。
※権限レベルは参照/更新がMAX

- 何を

  - レコード所有者ベースなのか
    - 公開グループ
    - ロール
    - ロール＆下位ロール
    - Roles, Internal and Portal Subordinates
  - 条件ベースなのか

- 誰に

  - 公開グループ
  - ロール
  - ロール＆下位ロール
  - Roles, Internal and Portal Subordinates

- アクセスレベル

  - 参照のみ
  - 参照/更新

  ---

##### Sharing rule

ユーザが所有する**個々のレコード**を共有することができる。
※組織レベルではなくユーザレベルで共有ができる。

誰に

- 公開グループ
- ロール
- ロール＆下位ロール
- ユーザ

アクセスレベル

- 参照のみ
- 参照/更新

##### 手动Share Button

- Sharing Setting for the Object or Related Object is Private or Public Read Only （OWD）
- 权限
  - User is Record Owner.
  - User is Administrator.
  - The user is in a role hierarchy above the record owner.
  - The User who has been granted **“Full Access” sharing.**