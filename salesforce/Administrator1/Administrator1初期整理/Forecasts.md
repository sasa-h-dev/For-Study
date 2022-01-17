# Forecasts

### Forecast Types

| OBJECT                                                       | MEASURE                                                      | DATE TYPE               | HIERARCHY           |
| :----------------------------------------------------------- | :----------------------------------------------------------- | :---------------------- | :------------------ |
| Opportunity                                                  | Amount (revenue)QuantityCustom currency (revenue) or number (quantity) | Close date              | TerritoryUser role  |
| Opportunity Product(Used for product family grouping and required for product date forecasts) | Total price (revenue)QuantityCustom currency (revenue) or number (quantity) | Close dateProduct date* | Territory*User role |
| Opportunity Split(Required for opportunity splits forecasts) | Amount (used with revenue, overlay, and custom currency split types)Custom currency (revenue) | Close date              | User role           |
| Line Item Schedule(Used for product family grouping and required for schedule date forecasts) | RevenueQuantityCustom currency (revenue) or number (quantity) | Schedule date           | TerritoryUser role  |

### Enable Forecast Adjustments

预测用户可以调整预测

- Enable manager adjustments

  要让预测经理调整其直接下属和子区域的金额，请启用经理调整。

- Enable owner adjustments

  若要让所有预测用户调整其自己预测的金额，包括他们自己的地区预测，请启用所有者调整。

### Enable Cumulative Forecast Rollups

启用累积预测汇总

默认预测显示包括每个预测类别中机会的单独汇总列：已关闭、提交、最有可能、最佳情况和管道。您可以选择显示累积汇总列，其中包括多个类别中的Opportunity。

仅关闭（仅关闭商机）

提交预测（已关闭+提交机会）

最佳案例预测（已完成+提交+最佳案例机会）

开放管道（提交+最佳案例+管道机会）

### Configure the Default Forecast Display

设定一个对公司最有意义的预测期。这些设置适用于所有预测类型。查看预测的用户可以更改范围。

Forecast Period

- Monthly
- MonthlyQuarterly

Starting on

- Current month

Display

- 6 months
