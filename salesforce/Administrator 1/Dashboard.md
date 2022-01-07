### Dashboard

Set up a Dynamic Dashboard

View Dashboard As

[参照](https://trailhead.salesforce.com/content/learn/modules/lex_implementation_reports_dashboards/lex_implementation_reports_dashboards_visualizing_data)

- Me 
- Another person
- The dashboard viewer
  - You can't follow components on dynamic dashboards.
  - You can’t save dynamic dashboards in private folders.
  - You can’t schedule refreshes for dynamic dashboards. They must be refreshed manually.
  - up to 5 dynamic dashboards for Enterprise Edition, 10 for Unlimited and Performance Edition, and 3 for Developer Edition. Dynamic dashboards aren’t available in other editions. 
- Let dashboard viewers choose whom they view the dashboard as
  - With the “View My Team’s Dashboards” user permission
  - With the “View All Data” user permission

次のユーザとしてダッシュボードを参照→実行ユーザを指定できる
ダッシュボードに表示されるデータは実行ユーザに指定したユーザがアクセスできるデータとなる。
ソースレポートを参照する結果についてはクリックしたユーザが参照できるレコードにおいて集計される



---

#### 動的ダッシュボード

実行ユーザがダッシュボード閲覧者に指定されているダッシュボード
各ユーザが参照できるデータが集計され表示される

※ダッシュボードの実行ユーザがグラフで使用されているレポートフォルダにアクセス権がない場合はそのグラフはエラーとなり表示されない。

---

### Access to Dashboard Folders

Public Folders

The following permissions apply to folders with these visibility settings:

- This folder is accessible by all users, including portal users
- This folder is accessible by all users, except for portal users

| ACCESS LEVEL  | PERMISSIONS NEEDED TO ACCESS READ-ONLY FOLDERS               | PERMISSIONS NEEDED TO ACCESS READ/WRITE FOLDERS              |
| :------------ | :----------------------------------------------------------- | :----------------------------------------------------------- |
| Read          | Run Reports                                                  | Run Reports                                                  |
| Write New     | All of the following:Run ReportsManage DashboardsView All Data | Both of the following:Run ReportsManage Dashboards           |
| Modify/Delete | All of the following:Run ReportsManage DashboardsView All Data | All of the following:Run ReportsManage DashboardsView All Data |

Hidden Folders

The following permissions apply to folders that have this visibility setting:

- This folder is hidden from all users

| ACCESS LEVEL  | PERMISSIONS NEEDED TO ACCESS READ-ONLY FOLDERS               | PERMISSIONS NEEDED TO ACCESS READ/WRITE FOLDERS              |
| :------------ | :----------------------------------------------------------- | :----------------------------------------------------------- |
| Read          | Both of the following:Run ReportsView All Data               | Both of the following:Run ReportsView All Data               |
| Write New     | All of the following:Run ReportsManage DashboardsView All Data | All of the following:Run ReportsManage DashboardsView All Data |
| Modify/Delete | All of the following:Run ReportsManage DashboardsView All Data | All of the following:Run ReportsManage DashboardsView All Data |

Shared Folders

| ACCESS LEVEL  | PERMISSIONS NEEDED TO ACCESS READ-ONLY FOLDERS               | PERMISSIONS NEEDED TO ACCESS READ/WRITE FOLDERS              |
| :------------ | :----------------------------------------------------------- | :----------------------------------------------------------- |
| Read          | Run Reports                                                  | Run Reports                                                  |
| Write New     | All of the following:Run ReportsManage DashboardsView All Data | Both of the following:Run ReportsManage Dashboards           |
| Modify/Delete | All of the following:Run ReportsManage DashboardsView All Data | All of the following:Run ReportsManage DashboardsView All Data |

ユーザにダッシュボードへのアクセス権を与えるためにはどうすべきか

- パブリックグループとフォルダを共有する
- ロールとフォルダを共有する