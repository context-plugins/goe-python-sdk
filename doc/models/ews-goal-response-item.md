
# Ews Goal Response Item

*This model accepts additional fields of type Any.*

## Structure

`EwsGoalResponseItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `goal_id` | `str` | Required | Goal identifier |
| `current_wealth` | `float` | Required | Current allocated wealth for this goal. |
| `infusions` | [`List[EwsSeriesValue]`](../../doc/models/ews-series-value.md) | Required | Cashflow timeline for this goal. |
| `goal_priority_order` | `int` | Required | Outputs the priority of the goal as inputted by the user or calculated by the algorithm.<br><br>**Constraints**: `>= 0` |
| `goal_amount` | `float` | Required | This is the bequestAmount + goalAmount(only if they lie on the cashflowDate).<br><br>**Constraints**: `>= 0` |
| `funded_status` | [`Fundedstatus`](../../doc/models/fundedstatus.md) | Required | Funding status of the goal |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.ews_goal_response_item import EwsGoalResponseItem
from goeapi.models.ews_series_value import EwsSeriesValue
from goeapi.models.fundedstatus import Fundedstatus

ews_goal_response_item = EwsGoalResponseItem(
    goal_id='goalId6',
    current_wealth=46.68,
    infusions=[
        EwsSeriesValue(
            value=7.58,
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    goal_priority_order=0,
    goal_amount=153.5,
    funded_status=Fundedstatus.FUNDED,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

