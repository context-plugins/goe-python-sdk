
# Priority 2

Used to classify a goal in, usually, one of the following categories. <br>                        Priority Name&emsp; Desired Probability <br>                        Need&emsp;&emsp;&emsp;&emsp;&emsp;85% <br>                        Want&emsp;&emsp;&emsp;&emsp;&emsp;70% <br>                        Wish&emsp;&emsp;&emsp;&emsp;&emsp;60% <br>                        Dream&emsp;&emsp;&emsp;&emsp;50% <br>                        The priority of a goal affects the recommendation. The recommendation is calibrated to the desired probability of a priority.<br>                        Note: <br>                        In case of multiple goals, the priority of the plan is determined by the highest priority goal within the plan

*This model accepts additional fields of type Any.*

## Enumeration

`Priority2`

## Fields

| Name |
|  --- |
| `NEED` |
| `WANT` |
| `WISH` |
| `DREAM` |

## Example

```python
from goeapi.models.priority_2 import Priority2

priority_2 = Priority2.NEED
```

