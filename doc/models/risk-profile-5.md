
# Risk Profile 5

Defines the user’s risk profile – does not vary by goal for each investor.             On a default basis, GOE is configured for three Risk Profile levels, but it can be customized for up to five levels.             Note that Risk Profiles are mapped to portfolio access.This is nullable and non mandatory if useCapsAndFloors is true

*This model accepts additional fields of type Any.*

## Enumeration

`RiskProfile5`

## Fields

| Name |
|  --- |
| `CONSERVATIVE` |
| `MODERATE` |
| `AGGRESSIVE` |

## Example

```python
from goeapi.models.risk_profile_5 import RiskProfile5

risk_profile_5 = RiskProfile5.AGGRESSIVE
```

