
# Upa Goal Response

*This model accepts additional fields of type Any.*

## Structure

`UpaGoalResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `goal_id` | `str` | Required | Goal identifier for individual goal. |
| `goal_amt` | `List[float]` | Required | Accumulation only Goals: Target wealth value associated with the goal at end of goal tenure.             Accumulation & Decumulation, and decumulation/income goals: Goal value (withdrawal)                 each year during decumulation period.<br><br>**Constraints**: `>= 0` |
| `start_date` | `str` | Required | Accumulation Goals: Beginning date of the goal - this is typically the date of initial             investment for accumulation goals.<br> Accumulation & Decumulation, and decumulation/income goals:                 Date when the first withdrawal/income starts. |
| `end_date` | `str` | Required | Accumulation Goals: End date of the goal - when a lumpsum is due. <br> Accumulation & Decumulation, and decumulation/income goals: Date of last withdrawal. |
| `priority` | [`Priority3`](../../doc/models/priority-3.md) | Required | Goal priority. |
| `modified_goal_amt` | `List[float]` | Required | Modified goal. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.priority_3 import Priority3
from goeapi.models.upa_goal_response import UpaGoalResponse

upa_goal_response = UpaGoalResponse(
    goal_id='Goal1',
    goal_amt=[
        183.09
    ],
    start_date='01-01-2021',
    end_date='01-01-2031',
    priority=Priority3.DREAM,
    modified_goal_amt=[
        76.72,
        76.73
    ],
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

