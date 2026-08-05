
# Goal Profile Simulation Engine

*This model accepts additional fields of type Any.*

## Structure

`GoalProfileSimulationEngine`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `goal_id` | `str` | Required | Uniquely identifies a goal |
| `start_date` | `str` | Required | Start date of the withdrawals |
| `end_date` | `str` | Required | End date of the withdrawals |
| `priority` | [`Priority2`](../../doc/models/priority-2.md) | Required | Used to classify a goal in, usually, one of the following categories. <br>                        Priority Name&emsp; Desired Probability <br>                        Need&emsp;&emsp;&emsp;&emsp;&emsp;85% <br>                        Want&emsp;&emsp;&emsp;&emsp;&emsp;70% <br>                        Wish&emsp;&emsp;&emsp;&emsp;&emsp;60% <br>                        Dream&emsp;&emsp;&emsp;&emsp;50% <br>                        The priority of a goal affects the recommendation. The recommendation is calibrated to the desired probability of a priority.<br>                        Note: <br>                        In case of multiple goals, the priority of the plan is determined by the highest priority goal within the plan |
| `goal_purpose` | `str` | Required | Used to especially identify “education” goals.             Does not impact any computation. |
| `goal_amt` | `List[float]` | Required | List of one or more withdrawals associated with a goal.                     The first withdrawal occurs on the “startDate”. The last withdrawal occurs on “endDate”,                     while the intermittent withdrawals occur on the “cashflowDate” – every year. |
| `scenario_type` | `str` | Required | “regular” or “retirement” depending on the type of goal.                         A regular goal often has a single withdrawal while a retirement goal has series of withdrawals. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.goal_profile_simulation_engine import GoalProfileSimulationEngine
from goeapi.models.priority_2 import Priority2

goal_profile_simulation_engine = GoalProfileSimulationEngine(
    goal_id='Goal1',
    start_date='19-09-2023',
    end_date='01-11-2032',
    priority=Priority2.NEED,
    goal_purpose='Non-education',
    goal_amt=[
        60000
    ],
    scenario_type='regular',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

