
# Scenariotype 2

‘regular’ for regular goals accumulation goals where cash flows are positive (contributions)             and with a typical target wealth.<br><br>            ‘retirement’ for scenarios where a decumulation period is included: <br>            1. Scenarios with an accumulation period (and an initial wealth) & positive cash flows followed by                 a decumulation period with withdrawals (negative cash flows) with or without an inheritance.<br>                    2. Scenarios with an initial wealth followed by a decumulation period with or without an inheritance.

*This model accepts additional fields of type Any.*

## Enumeration

`Scenariotype2`

## Fields

| Name |
|  --- |
| `REGULAR` |
| `RETIREMENT` |

## Example

```python
from goeapi.models.scenariotype_2 import Scenariotype2

scenariotype_2 = Scenariotype2.REGULAR
```

