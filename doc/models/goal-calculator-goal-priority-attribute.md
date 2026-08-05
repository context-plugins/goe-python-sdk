
# Goal Calculator Goal Priority Attribute

Defines the importance a goal holds for a specific user. Order of priority is Need > Want > Wish > Dream          goalPriority can be from 1 to 4 levels. However, note that Goal priority defines the target probabilities and the loss threshold values.

*This model accepts additional fields of type Any.*

## Enumeration

`GoalCalculatorGoalPriorityAttribute`

## Fields

| Name |
|  --- |
| `NEED` |
| `WANT` |
| `WISH` |
| `DREAM` |

## Example

```python
from goeapi.models.goal_calculator_goal_priority_attribute import GoalCalculatorGoalPriorityAttribute

goal_calculator_goal_priority_attribute = GoalCalculatorGoalPriorityAttribute.NEED
```

