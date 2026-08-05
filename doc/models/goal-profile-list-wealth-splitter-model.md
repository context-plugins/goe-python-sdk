
# Goal Profile List Wealth Splitter Model

*This model accepts additional fields of type Any.*

## Structure

`GoalProfileListWealthSplitterModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `goal_id` | `str` | Required | Unique identifier for each goal |
| `goal_value` | `float` | Required | Target goal amount |
| `purpose` | `str` | Required | Type of goal (for example, ‘Children’s education, Vacation, etc.’) |
| `curr_wealth` | `float` | Required | Current wealth allocated for the goal when the Initial Wealth Splitter is being called or executed. |
| `cashflow_date` | `str` | Optional | Cashflow date of the goal - this is the date (year is ignored) on which infusions/withdrawals                                                                 would be realized for the goal. Format is "dd-mm-yyyy"                                                                  If not passed or value is null, the algorithm would consider the first reallocation date as the cashflow date. |
| `goal_start_date` | `str` | Optional | Defines the goal's start date. Must be greater than or equal to the startDate field and in DD-MM-YYYY format. Default value is Null. |
| `goal_priority` | [`WeathSplitterGoalPriorityAttribute`](../../doc/models/weath-splitter-goal-priority-attribute.md) | Required | Defines the importance a goal holds for a specific user. Order of priority is Need > Want > Wish > Dream  <br>         goalPriority can be from 1 to 4 levels. However, note that Goal priority defines the target probabilities and the loss threshold values.         For example, goals with a higher priority (e.g. Need) would have a higher target goal probability (85%) with a higher (aggressive) loss threshold value (slightly more than IW value) in the current set-up.         This needs to be re-mapped based on the number of goal-priority levels, in case of a change. |
| `cashflow_type` | `str` | Required | Describes the cash flow frequency.                                         Valid input is ‘yearly’ or ‘monthly’.                                         This parameter is provided to account for real-world investors who might put in monthly infusions as opposed to yearly infusions.                                         Monthly infusions would be smaller in value (and hence easier to commit to) vs. yearly infusions. |
| `cashflow` | `List[float]` | Required | Cashflow array – includes any cash infusions and/or withdrawals; length would depend on cashflow_type and the goal tenure |
| `end_date` | `str` | Required | Defines the end date of goal.Valid input format is date – ‘dd-mm-yyyy’ |
| `scenario_type` | [`ScenarioType3`](../../doc/models/scenario-type-3.md) | Required | Determines the type of the scenario, the suggested portfolio and the wealth glide path is created accordingly.                                             ‘regular’ for regular goals accumulation goals where cash flows are positive (contributions) and with a typical target wealth                                             ‘retirement’ for scenarios where a decumulation period is included: <br>                                             1.	Scenarios with an accumulation period (and an initial wealth) & positive cash flows followed by a decumulation period with withdrawals (negative cash flows) with or without an inheritance <br>                                             2.	Scenarios with an initial wealth followed by a decumulation period with or without an inheritance |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.goal_profile_list_wealth_splitter_model import GoalProfileListWealthSplitterModel
from goeapi.models.scenario_type_3 import ScenarioType3
from goeapi.models.weath_splitter_goal_priority_attribute import WeathSplitterGoalPriorityAttribute

goal_profile_list_wealth_splitter_model = GoalProfileListWealthSplitterModel(
    goal_id='Goal_1',
    goal_value=1000000,
    purpose='Saving',
    curr_wealth=829415,
    goal_priority=WeathSplitterGoalPriorityAttribute.NEED,
    cashflow_type='monthly',
    cashflow=[
        0,
        0,
        0,
        0
    ],
    end_date='01-01-2033',
    scenario_type=ScenarioType3.RETIREMENT,
    cashflow_date='15-06-2020',
    goal_start_date='goalStartDate0',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

