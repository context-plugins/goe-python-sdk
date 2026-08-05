
# Ews Goal Profile

*This model accepts additional fields of type Any.*

## Structure

`EwsGoalProfile`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `goal_profile_list` | [`List[EwsGoalProfileItem]`](../../doc/models/ews-goal-profile-item.md) | Required | List containing the details of all goals for the investor. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.ews_goal_profile import EwsGoalProfile
from goeapi.models.ews_goal_profile_item import EwsGoalProfileItem
from goeapi.models.goalfrequency import Goalfrequency
from goeapi.models.goalpriority import Goalpriority
from goeapi.models.scenariotype import Scenariotype

ews_goal_profile = EwsGoalProfile(
    goal_profile_list=[
        EwsGoalProfileItem(
            goal_amount=79.94,
            goal_start_date='goalStartDate6',
            goal_end_date='goalEndDate6',
            goal_id='goalId2',
            goal_priority=Goalpriority.DESIRE,
            scenario_type=Scenariotype.REGULAR,
            goal_frequency=Goalfrequency.MONTHLY,
            bequest_amount=0,
            goal_name='goalName4',
            goal_type='goalType6',
            goal_rank=32,
            current_portfolio_id=228,
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

