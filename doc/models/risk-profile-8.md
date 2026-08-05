
# Risk Profile 8

Defines the user’s overall risk profile – does not vary by goal for each investor.         On a default basis, GOE is configured for three Risk Profile levels, but it can be customized for up to five levels.

*This model accepts additional fields of type Any.*

## Enumeration

`RiskProfile8`

## Fields

| Name |
|  --- |
| `CONSERVATIVE` |
| `MODERATE` |
| `AGGRESSIVE` |

## Example

```python
from goeapi.models.risk_profile_8 import RiskProfile8

risk_profile_8 = RiskProfile8.MODERATE
```

