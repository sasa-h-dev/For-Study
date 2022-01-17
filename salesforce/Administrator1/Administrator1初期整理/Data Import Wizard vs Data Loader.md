### Data Import Wizard vs Data Loader

| **Data Import Wizard**                                       | **Data Loader**                                    |
| ------------------------------------------------------------ | -------------------------------------------------- |
| For simple imports of data                                   | For complex imports of data                        |
| up to 50,000 records.                                        | up to 5,000,000 records.                           |
| It supports all the custom objects and only a few standard objects like Account, Contact, Campaign members, person accounts, Leads, and Solution. | All Objects                                        |
| It supports schedule export.                                 | It doesn’t support scheduled export.               |
| Delete operation is not available.                           | Delete operation is available.                     |
| Cannot import cases and opportunity.                         | Can import cases, events, tasks, and opportunities |
| While importing, duplicates can be ignored.                  | While importing, duplicates cannot be ignored.     |
| Stop Workflow Rules                                          | Can't stop Workflow Rules                          |
| It doesn’t require installation.                             | It requires installation.                          |
|                                                              |                                                    |

---

Which set of Salesforce records is exported by choosing the "Export AII" option instead of "Export" in Data Loader?

**A.** Records for a specified object and its child records.

**B.** Records for all standard objects in the org.

**C.** Records for a specified object including records in the recycle bin

**D.** Records for a specified object and its parent records.

Correct Answer: C

