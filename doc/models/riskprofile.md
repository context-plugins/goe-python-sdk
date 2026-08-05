
# Riskprofile

The risk tolerance profile selected by the user. This is defined at the user level, not per goal.

*This model accepts additional fields of type Any.*

## Enumeration

`Riskprofile`

## Fields

| Name |
|  --- |
| `CONSERVATIVE` |
| `MODERATE` |
| `AGGRESSIVE` |

## Example

```python
from goeapi.models.riskprofile import Riskprofile

riskprofile = Riskprofile.CONSERVATIVE
```

