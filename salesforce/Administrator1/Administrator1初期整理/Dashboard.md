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

---

### Chart Types

Bar Chart

Line Chart

Donut Chart

Metric Chart

Gauge Chart

Funnel Chart

Scatter Chart

Lightning Table

---

### Dashboard Permission Access

- Change Dashboard Colors
- Create and Customize Dashboards
- Create Dashboard Folders
- Edit My Dashboards
- Manage All Private Reports and Dashboards
- **Manage Dashboards in Public Folders**
- Manage Dynamic Dashboards
- Subscribe to Dashboards
- Subscribe to Dashboards: Add Recipients	
- Subscribe to Dashboards: Send to Groups and Roles
- View Dashboards in Public Folders
- Drag-and-Drop Dashboard Builder
- View My Team's Dashboards

---

Go to the California Sales Dashboards Folder, Share, and choose Edit access for the Sales Manager.

**Viewer**

- View a folder in the folder tree
- View all contents (Run Report, Refresh Dashboard)

**Editor**

- Everything from Viewer access plus:
  - Edit all contents of a folder
  - Add contents to folder
  - Delete contents from folder

**Manager**

- Everything from Editor access plus:
  - Edit folder name
  - Edit/delete/remove shares

---

### Post Snapshots of Dashboard Components to Chatter

[文档](https://help.salesforce.com/s/articleView?id=sf.dashboards_post_to_dashboard_feed.htm&type=5)

---

Which three reports can be used to display a list of the Top 10 Accounts on a dashboard? Choose 3 answers

**A.** Summary report without a chart

**B.** Summary report with Rows to Display set to 10

**C.** Tabular report with a chart

**D.** Summary report with a chart

**E.** Tabular report with Rows to Display set to 10

Correct Answer: A,D,E

---

How many components can be added in a single column of dashboard?

**A.** Unlimited

**B.** 10

**C.** 17

**D.** 23

Correct Answer: B

---

The District Sales Director at Cloud Kicks wants to share the leaderboard component on his dashboard with his sales team.
What two actions should an administrator take to enable this functionality?
Choose 2 answers

**A.** Build a Reporting Snapshot

**B.** Turn on Chatter Feed Tracking for Dashboards

**C.** Enable Opportunity Teams

**D.** Create a Chatter group for the Sales Team

