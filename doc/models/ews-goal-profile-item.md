
# Ews Goal Profile Item

*This model accepts additional fields of type Any.*

## Structure

`EwsGoalProfileItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `goal_amount` | `float` | Required | The withdrawal amount for the goal, disbursed at every cashflow date from the goal start date to the goal end date.<br><br>**Constraints**: `>= 0` |
| `bequest_amount` | `float` | Optional | The final wealth amount withdrawn at the investment end date, in addition to the goal amount. This number has to be zero or greater than zero if not null.<br><br>**Default**: `0` |
| `goal_start_date` | `str` | Required | The date when the goal begins to be realized. |
| `goal_end_date` | `str` | Required | The date when the goal realization ends. For regular scenarios, the end date is the same as the goal start date. |
| `goal_id` | `str` | Required | A unique identifier for each goal. |
| `goal_name` | `str` | Optional | A descriptive name for the goal to aid identification. |
| `goal_type` | `str` | Optional | Type of goal used to map accounts to the goals. |
| `goal_priority` | [`Goalpriority`](../../doc/models/goalpriority.md) | Required | Specifies the importance level of the goal for the investor. Priority order: Need > Want > Wish > Dream > Desire |
| `scenario_type` | [`Scenariotype`](../../doc/models/scenariotype.md) | Required | Specifies the goal scenario type. Same as in RunPipe API. |
| `goal_frequency` | [`Goalfrequency`](../../doc/models/goalfrequency.md) | Required | Specifies the frequency at which goal withdrawals occur. |
| `goal_rank` | `int` | Optional | The numerical priority rank assigned to the goal |
| `current_portfolio_id` | `int` | Optional | The existing portfolio ID recommended for the goal in the previous EWS call, used for swing calculations. |
| `portfolio_set_label` | `str` | Optional | The configuration and portfolio set associated with the goal |
| `account_mapping` | List[[EwsAccountMappingItem](../../doc/models/ews-account-mapping-item.md)] \| None | Optional | This is a container for any-of cases. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.ews_goal_profile_item import EwsGoalProfileItem
from goeapi.models.goalfrequency import Goalfrequency
from goeapi.models.goalpriority import Goalpriority
from goeapi.models.scenariotype import Scenariotype

ews_goal_profile_item = EwsGoalProfileItem(
    goal_amount=147.72,
    goal_start_date='goalStartDate4',
    goal_end_date='goalEndDate8',
    goal_id='goalId4',
    goal_priority=Goalpriority.WISH,
    scenario_type=Scenariotype.REGULAR,
    goal_frequency=Goalfrequency.MONTHLY,
    bequest_amount=0,
    goal_name='goalName2',
    goal_type='goalType8',
    goal_rank=102,
    current_portfolio_id=162,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

