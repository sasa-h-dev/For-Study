### Workflow VS Process builder

启动条件

| **workflow**                                                 | **Process builder**                  |
| ------------------------------------------------------------ | ------------------------------------ |
| created                                                      | a  record changes                    |
| created, and every time it's edit                            | A platform event message is received |
| created, and any time it's edited to subsequently meet criteria | It’s invoked by another process      |

Actions

| **workflow**     | **Process builder**                                          |
| ---------------- | ------------------------------------------------------------ |
| Task             | Apex<br />(The Apex class must have an invocable method.)    |
| Email Alert      | Create a Record (any object)                                 |
| Field Update     | Email Alerts                                                 |
| Outbound Message | Flows                                                        |
|                  | Post to Chatter                                              |
|                  | Processes<br />(Only active invocable processes can be started by a process.) |
|                  | Quick Actions                                                |
|                  | Quip                                                         |
|                  | Send Custom Notification                                     |
|                  | Submit for Approval                                          |
|                  | Update Records <br />(Record that started your process or a record related to the sobject) |

