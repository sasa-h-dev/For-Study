---

メタデータを2つの異なる本番組織に移行するために使用する必要があるツールは何ですか？

- Force.Com IDE
- Force.Com移行ツール
- 管理されていないパッケージ

---

ソーシャルアカウントについて正しいのはどれですか？

- ソーシャルアカウントデータを表示するには、個人のソーシャルアカウントが必要です。

---

当检索到的数据是0条时候

```java
// Error: System.QueryException: List has no rows for assignment to SObject
// 1.
Contact con = [SELECT ID,FirstName,LastName,Email FROM Contact WHERE LastName = 'Smith'];
System.debug(con);

// 2.
string lastName = 'Smith';
string query= 'SELECT ID,FirstName,LastName,Email FROM Contact WHERE LastName = :lastName';
Contact con = Database.query(query);
System.debug(con);
```

```java
List<Contact> con = [SELECT ID,FirstName,LastName,Email FROM Contact WHERE LastName = 'Smith'];
System.debug(con); // ()

string lastName = 'Smith';
string query= 'SELECT ID,FirstName,LastName,Email FROM Contact WHERE LastName = :lastName';
List<Contact> con = Database.query(query);
System.debug(con); // ()
```

---

ユーザーページレイアウトのアクションに関係なく、ユーザープロファイルページに表示される標準的なChatterアクションは何ですか？

- 投稿

- 感謝
- ファイル

#### standard Chatter actions

- Post
- Poll
- Question
- Announcements

 Salesforce Classic standard actions also include File, Link, and Thanks (WDC)

- File
- Link
- Thanks (WDC)

---

ユーザーがオブジェクト固有の作成アクションを使用してレコードを作成すると、そのレコードのどのフィードアイテムが表示されますか？

- レコードを作成したユーザーのChatterフィード
- 新しいレコードが作成されたレコードのフィード
- レコードが作成されたレコードをフォローする最初のユーザーのChatterフィード

---

## 問26

次の項目のうち、レコードタイプに使用できないものはどれですか？

A.商談のフェーズ
B.ケースの状況
C.ソリューションの状況
D.リードの状況
E.上記のすべて

答え

E.上記のすべて

---

Lightningコンポーネントはどの3つの製品で利用できますか？

- Salesforceモバイルアプリ
- コミュニティ
- Lightning Experience

---

開発者は、複雑なトリガーロジックを処理するApexヘルパークラスを作成します。
トリガーがDMLガバナーの制限を超えたときに、ヘルパークラスはどのようにユーザーに警告できますか？

- Limits.getDMLRows（）を使用し、DMLステートメントの数を超える前にエラーメッセージを表示する。

---

デバッグログフィルター設定はどこで設定できますか？

- デバッグログのレコードの[詳細を表示]リンク。
- クラスまたはトリガーの詳細ページの[ログフィルター]タブ。

---

## 問44

販売管理チームは新しいインターンを雇用します。 インターンは商談を表示することはできませんが、取引先レコードを表示するときは、すべての商談の最新の完了日を表示する必要があります。
開発者はこの要件を満たすために何をしますか？

A.親取引先のフィールドを更新するワークフローオブジェクトのワークフロールールを作成します。
B.AccountオブジェクトにOpportunity Close Dateフィールドで最大を表示する数式フィールドを作成します。
C.AccountオブジェクトにOpportunity Close Dateフィールドの最大を表示する積み上げ集計フィールドを作成する
D.最新の商談のクローズ日を照会するトリガーをAccountオブジェクトに作成します。

答え

C.AccountオブジェクトにOpportunity Close Dateフィールドの最大を表示する積み上げ集計フィールドを作成する

---

## 問54

Salesforce AppExchangeからパッケージをインストールおよびアンインストールするには、どの権限が必要ですか？

A.パッケージライセンスの管理
B. AppExchangeパッケージをアップロードする
C. AppExchangeパッケージをダウンロードする
D. AppExchangeパッケージを作成する

答え

C. AppExchangeパッケージをダウンロードする

---

## 問57

Apexクラスとインターフェースに関する有効なステートメントは何ですか？

A.例外クラスは、Exceptionという単語で終わる必要があります。
B.クラスは、複数のレベルの内部クラスを持つことができます。
C.クラスのデフォルト修飾子はprivateです。
D.インターフェイスのデフォルト修飾子はプライベートです。

答え

A.例外クラスは、Exceptionという単語で終わる必要があります。
C.クラスのデフォルト修飾子はprivateです。



To define a class, specify the following:

1. Access modifiers:
   - You must use one of the access modifiers (such as public or global) in the declaration of a top-level class.
   - You do not have to use an access modifier in the declaration of an inner class.
2. Optional definition modifiers (such as virtual, abstract, and so on)
3. Required: The keyword class followed by the name of the class
4. Optional extensions and/or implementations

```java
public class myOuterClass {
   // Additional myOuterClass code here
   class myInnerClass {
     // myInnerClass code here
   }
}
```

---

## 問58

階層カスタム設定は、Salesforceの各プロファイルの特定のURLを保存します。
開発者は、どのステートメントを使用して現在のユーザーのプロファイルの正しいURLを取得し、このVisualforceページを表示できますか？

A. {$ Setup.Url_Settings_c.Instance [Profile.Id] .URL__c}
B. {！$ Setup.Url_Settings_c.URL__c}
C. {！$ Setup.Url_Settings_c [Profile.Id、URL__c}
D. {！$ Setup.Url_Settings_c [$ Profile.Id、URL__c}

答え

B. {！$ Setup.Url_Settings_c.URL__c}

---

## 問59

APIベースのツールを使用してレコードを挿入するとき、開発者は何を考慮する必要がありますか？

A.ページレイアウトの必須フィールドが適用されます。
B.必須項目の設定が適用されます。
C. Apexトリガーは無視されます。
D.検証ルールが適用されます。

答え

C. Apexトリガーは無視されます。
D.検証ルールが適用されます。

---

## 問64

ユニバーサルコンテナには、アカウントへの参照関係を持つカスタムオブジェクト「サービス」があります。 ユニバーサルコンテナーは、アカウントマネージャーがアカウントを見ながらアカウントに新しいサービスを入力できるアクションでSalesforce1を強化したいですか？

A.サービスにオブジェクト固有のアクションを入力し、アカウントレイアウトに配置します
B.サービスにオブジェクト固有のアクションを入力し、サービスレイアウトに配置する
C.アカウントにオブジェクト固有のアクションを入力し、アカウントレイアウトに配置する
D.アカウントにオブジェクト固有のアクションを入力し、サービスレイアウトに配置する

答え

C.アカウントにオブジェクト固有のアクションを入力し、アカウントレイアウトに配置する

---

## 問65

Lightnningページはどれですか？

A.カスタマーコミュニティからアクセスできるページ。
B. Salesforceページレイアウトの新しい名前。
C. Salesforce1でページを作成するためのカスタムレイアウト。
D.コンパクトで構成可能な再利用可能な要素

答え

C. Salesforce1でページを作成するためのカスタムレイアウト。

---

## 問88

開発者はApexクラスにメソッドを作成し、エラーが適切に処理されるようにする必要があります。 開発者は何を使用しますか？

A. ApexPages.addErrorMessage()
B.カスタム例外
C. .addError()
D. Database.handleException()
E. try / catchコンストラクト

答え

B.カスタム例外
C. .addError()
E. try / catchコンストラクト

---

## 問99

積み上げ集計項目に関して正しい記述はどれですか？ 該当するものをすべて選択

A.高度な通貨管理は、積み上げ集計項目に影響しません。
B.積み上げ集計項目は編集ページに表示されないため、検証ルールで使用できますが、検証のエラーの場所としては使用できません。
C.詳細またはマスターレコードのいずれかを保存すると、検証エラーが表示される場合があります。
D.現在の日付や現在のユーザーなどの自動導出フィールドは、積み上げ集計フィールドで許可されます。
E.作成後、選択した詳細オブジェクトを変更したり、ロールアップサマリー定義で参照されているフィールドを削除したりすることはできません。

答え

B.積み上げ集計項目は編集ページに表示されないため、検証ルールで使用できますが、検証のエラーの場所としては使用できません。
C.詳細またはマスターレコードのいずれかを保存すると、検証エラーが表示される場合があります。
E.作成後、選択した詳細オブジェクトを変更したり、ロールアップサマリー定義で参照されているフィールドを削除したりすることはできません。

---

## 問100

SOQLクエリのwhere句で有効なものは何ですか？

A.位置情報フィールド。
B.暗号化されたフィールド。
C.集約関数。
D.エイリアス表記。

答え

A.位置情報フィールド。
D.エイリアス表記。

---

A developer is asked to create a Visualforce page that displays some Account fields as well as fields configured on the page layout for related Contacts.
How should the developer implement this request?

**A.** Create a controller extension.

**B.** Add a method to the standard controller.

**C.** Use the <apex:relatedList> tag.

**D.** Use the <apex:include> tag.

Correct Answer: C

---

What are three techniques that a developer can use to invoke an anonymous block of code? (Choose three.)

**A.** Create and execute a test method that does not specify a runAs() call.

**B.** Type code into the Developer Console and execute it directly.

**C.** Use the SOAP API to make a call to execute anonymous code.

**D.** Create a Visualforce page that uses a controller class that is declared without sharing.

**E.** Run code using the Anonymous Apex feature of the Developer's IDE.

Correct Answer: B,C,E

---

Which three statements are true regarding trace flags? (Choose three.)

**A.** Trace flags override logging levels.

**B.** Logging levels override trace flags.

**C.** Setting trace flags automatically cause debug logs to be generated.

**D.** Trace flags can be set in the Developer Console, Setup, or using the Tooling API.

**E.** If active trace flags are not set, Apex tests execute with default logging levels.

Correct Answer: A,D,E

---

A developer has a Visualforce page and custom controller to save Account records. The developer wants to display any validation rule violation to the user. How can the developer make sure that validation rule violations are displayed?

**A.** Use a try/catch with a custom exception class.

**B.** Add cuatom controller attributes to display the message.

**C.** Include <apex:message> on the Visualforce page.

**D.** Perform the DML using the Database.upsert() method.

Correct Answer: C

---

Which two are best practices when it comes to component and application event handling? (Choose two.)

**A.** Try to use application events as opposed to component events.

**B.** Use component events to communicate actions that should be handled at the application level.

**C.** Reuse the event logic in a component bundle, by putting the logic in the helper.

**D.** Handle low-level events in the event handler and re-fire them as higher-level events.

Correct Answer: C,D

---

Which three data types can a SOQL query return? Choose 3 answers

**A.** sObject

**B.** List

**C.** Long

**D.** Integer

Correct Answer: A,B,D

---

A developer wrote Apex code that calls out to an external system. How should a developer write the test to provide test coverage?

**A.** Write a class that extends WebserviceMock

**B.** Write a class that implements the WebserviceMock interface.

**C.** Write a class that implements the HTTPCalloutMock interface.

**D.** Write a class that extends HTTPCalloutMock.

Correct Answer: C

---

A developer needs to create a custom Interface in Apex.
Which three considerations must the developer keep in mind while developing the Apex Interface' Choose 3 answers

**A.** A method defined In an Apex Interface cannot have an access modifier.

**B.** The Apex class must be declared using the interface keyword.

**C.** New methods can be added to a public interface within a released package.

**D.** The Apex interface class access modifier can be set to Private, Public, or Global.

**E.** A method implementation can be defined within the Apex Interface.

Correct Answer: A,B,E

---

Which two statements are true about Getter and Setter methods as they relate to Visualforce?

**A.** A corresponding Setter method is required for each Getter method.

**B.** Getter methods pass values from a controller to a page.

**C.** There is no guarantee for the order in which Getter methods are called.

**D.** Setter methods always have to be declared global.

Correct Answer: A,B

---

A developer must troubleshoot to pinpoint the causes of performance issues when a custom page loads in their org. Which tool should the developer use to troubleshoot?

**A.** Visual Studio Core IDE

**B.** AppExchange

**C.** Developer Console

**D.** Salesforce CLI

Correct Answer: C

---

設定サンドボックスでメールを送信するためのワークフロールールを作成しました。 何らかの理由で機能していませんが、何を確認する必要がありますか？ （2つ選択）

- 配信設定を確認する
- 正しいメールアドレスを持っている

---

ユーザーがオブジェクト固有の作成アクションを使用してレコードを作成すると、そのレコードのどのフィードアイテムが表示されますか？（3つ選択）

- 新しいレコードが作成されたレコードのフィード
- レコードを作成したユーザーのChatterフィード
- 新しいレコードのフィードの最初のエントリ

---

メタデータを2つの異なる本番組織に移行するために使用する必要があるツールは何ですか？

- 管理されていないパッケージ
- Force.Com移行ツール
- Force.Com IDE

---

