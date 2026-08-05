
# Priority

Defines the importance a goal holds for a specific user.          Order of priority is Need > Want > Wish > Dream. Goal priority defines the target probabilities and             the loss threshold values. For example, goals with a higher priority (e.g. Need) would have a                  higher target goal probability (85%) with a higher (aggressive) loss threshold value.

*This model accepts additional fields of type Any.*

## Enumeration

`Priority`

## Fields

| Name |
|  --- |
| `NEED` |
| `WANT` |
| `WISH` |
| `DREAM` |
| `P1` |
| `P2` |
| `P3` |

## Example

```python
from goeapi.models.priority import Priority

priority = Priority.WISH
```

