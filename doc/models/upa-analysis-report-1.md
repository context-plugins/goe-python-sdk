
# Upa Analysis Report 1

<b>For the Original Plan:</b><br>            GOE’s outputs including probability, portfolio advice, etc.

*This model accepts additional fields of type Any.*

## Structure

`UpaAnalysisReport1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `current_goal_probability` | `float` | Required | GOE’s estimated probability to achieve the goal target wealth.<br><br>**Constraints**: `>= 0` |
| `recommended_portfolio_id` | `int` | Required | GOE’s current recommended portfolio index. |
| `meet_goal_priority` | `bool` | Required | Checks if goal probability is more than the target probability corresponding to the goal             priority – Target probabilities for all goal priorities (Need, Want, Wish and Dream) are set in the GOE config. |
| `is_goal_realistic` | `bool` | Required | To understand if the goal probability is more than 35% (This is a configurable field). |
| `one_time_top_up` | `float` | Required | Suggested one-time top-up amount that aims to improve the goal probability to meet the target goal probability. |
| `cashflow_recommendation` | [`CashflowRecommendation1`](../../doc/models/cashflow-recommendation-1.md) | Required | Cashflow recommendation is at the plan level.Note: -               Empty in case plan meets the target probability. |
| `bankruptcy_msg` | `str` | Required | Message flagging an expected bankruptcy (goal running out of money) in any year. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.cashflow_recommendation_1 import CashflowRecommendation1
from goeapi.models.upa_analysis_report_1 import UpaAnalysisReport1

upa_analysis_report_1 = UpaAnalysisReport1(
    current_goal_probability=10000,
    recommended_portfolio_id=6,
    meet_goal_priority=False,
    is_goal_realistic=False,
    one_time_top_up=38859,
    cashflow_recommendation=CashflowRecommendation1(
        cash_flow_monthly=None,
        cash_flow_yearly=2503,
        start_date='01-01-2022',
        end_date='01-01-2036',
        new_plan_prob=0.85,
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    bankruptcy_msg='NA',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

