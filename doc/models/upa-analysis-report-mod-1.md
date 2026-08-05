
# Upa Analysis Report Mod 1

<b>For the modified Plan:</b><br>            GOE’s outputs including probability, portfolio advice, etc.

*This model accepts additional fields of type Any.*

## Structure

`UpaAnalysisReportMod1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `current_goal_probability` | `float` | Required | GOE’s estimated probability to achieve the goal target wealth<br><br>**Constraints**: `>= 0` |
| `recommended_portfolio_id` | `int` | Required | GOE’s current recommended portfolio index. |
| `meet_goal_priority` | `bool` | Required | Checks if goal probability is more than the target probability corresponding to the goal         goalAmt    priority – Target probabilities for all goal priorities (Need, Want, Wish and Dream) are set in the GOE config. |
| `is_goal_realistic` | `bool` | Required | To understand if the goal probability is more than 35% (This is a configurable field). |
| `one_time_top_up` | `float` | Required | Suggested one-time top-up amount that aims to improve the goal probability to meet the target goal probability. |
| `cashflow_recommendation` | [`CashflowRecommendation1`](../../doc/models/cashflow-recommendation-1.md) | Required | Cashflow recommendation is at the plan level.Note: -               Empty in case plan meets the target probability. |
| `bankruptcy_msg` | `str` | Required | Message flagging an expected bankruptcy (goal running out of money) in any year. |
| `goals_response` | [`List[UpaGoalResponse]`](../../doc/models/upa-goal-response.md) | Required | - |
| `comments` | `str` | Required | Comment would describe the modifications or % change in goal amount made to original goal amounts to meet the target goal probability. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.cashflow_recommendation_1 import CashflowRecommendation1
from goeapi.models.priority_3 import Priority3
from goeapi.models.upa_analysis_report_mod_1 import UpaAnalysisReportMod1
from goeapi.models.upa_goal_response import UpaGoalResponse

upa_analysis_report_mod_1 = UpaAnalysisReportMod1(
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
    goals_response=[
        UpaGoalResponse(
            goal_id='Goal1',
            goal_amt=[
                179.05
            ],
            start_date='01-01-2021',
            end_date='01-01-2031',
            priority=Priority3.DREAM,
            modified_goal_amt=[
                72.68,
                72.69
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    comments='To meet all goals optimally as per their assigned priorities Goal1 has been reduced by 100.0%, Goal2 has been reduced by 50.0% of its original value. The allocated portfolio has an 94.316% probability of meeting the modified goals',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

