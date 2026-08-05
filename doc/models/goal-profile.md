
# Goal Profile

*This model accepts additional fields of type Any.*

## Structure

`GoalProfile`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `goal_id` | `str` | Required | Goal identifier for individual goal. |
| `goal_amt` | `List[float]` | Required | Accumulation only Goals: <br>              Target wealth value associated with the goal at end of goal tenure.               Accumulation & Decumulation, and decumulation/income goals: goal value (withdrawal) each year                  during the decumulation period. For subsequent calls, the goalAmt list needs to be updated based on the time that has elapsed.<br><br>**Constraints**: `>= 0` |
| `start_date` | `str` | Required | Accumulation Goals: beginning date of the goal - this is typically the date of initial investment for accumulation goals. For subsequent calls, the original start date for the goal needs to be passed.                           Accumulation & Decumulation, and decumulation/income goals: date when the first withdrawal/income starts. For subsequent calls, the original start date (date of first withdrawal) for the goal needs to be passed. |
| `end_date` | `str` | Required | Accumulation Goals: end date of the goal - when a lumpsum is due.                        Accumulation & Decumulation, and decumulation/income goals: date of last withdrawal. |
| `priority` | [`Priority`](../../doc/models/priority.md) | Required | Defines the importance a goal holds for a specific user.          Order of priority is Need > Want > Wish > Dream. Goal priority defines the target probabilities and             the loss threshold values. For example, goals with a higher priority (e.g. Need) would have a                  higher target goal probability (85%) with a higher (aggressive) loss threshold value. |
| `scenario_type` | [`Scenariotype2`](../../doc/models/scenariotype-2.md) | Required | ‘regular’ for regular goals accumulation goals where cash flows are positive (contributions)             and with a typical target wealth.<br><br>            ‘retirement’ for scenarios where a decumulation period is included: <br>            1. Scenarios with an accumulation period (and an initial wealth) & positive cash flows followed by                 a decumulation period with withdrawals (negative cash flows) with or without an inheritance.<br>                    2. Scenarios with an initial wealth followed by a decumulation period with or without an inheritance. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.goal_profile import GoalProfile
from goeapi.models.priority import Priority
from goeapi.models.scenariotype_2 import Scenariotype2

goal_profile = GoalProfile(
    goal_id='Goal1',
    goal_amt=[
        41400,
        41400,
        41400,
        41400,
        41400
    ],
    start_date='01-01-2022',
    end_date='01-01-2026',
    priority=Priority.NEED,
    scenario_type=Scenariotype2.RETIREMENT,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

