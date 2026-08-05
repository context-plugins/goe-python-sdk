
# Analysis Report Mod 1

In the event the original plan doesn’t meet the desired probability (in line with the priority),                     the plan is modified by dropping less important goal – denoted by lower priority.-                     This section gives details of the GOE run for the modified plan.                     Please note that the modification of goals is driven by business logic.

*This model accepts additional fields of type Any.*

## Structure

`AnalysisReportMod1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `goals_response` | [`List[GoalsResponse]`](../../doc/models/goals-response.md) | Required | Details of original and modified goal |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.analysis_report_mod_1 import AnalysisReportMod1
from goeapi.models.goals_response import GoalsResponse

analysis_report_mod_1 = AnalysisReportMod1(
    goals_response=[
        GoalsResponse(
            goal_id='Goal2',
            goal_amt=[
                179.05
            ],
            start_date='01-12-2023',
            end_date='30-11-2025',
            modified_goal_amt=[
                72.68,
                72.69
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

