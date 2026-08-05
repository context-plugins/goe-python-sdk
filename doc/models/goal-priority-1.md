
# Goal Priority 1

Defines the importance a goal holds for a specific user. Order of priority is Need > Want > Wish > Dream          goalPriority can be from 1 to 4 levels. However, note that Goal priority defines the target probabilities and the loss threshold values.

*This model accepts additional fields of type Any.*

## Enumeration

`GoalPriority1`

## Fields

| Name |
|  --- |
| `NEED` |
| `WANT` |
| `WISH` |
| `DREAM` |

## Example

```python
from goeapi.models.goal_priority_1 import GoalPriority1

goal_priority_1 = GoalPriority1.NEED
```

