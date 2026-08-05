
# Risk Profile 2

Defines the user’s risk profile. Note that Risk Profiles are mapped to portfolio access.             For example, a Conservative investor has access to portfolios 1-8 (or 50% Equity) while an Aggressive             investor has access to all 16 portfolios (up to 90% Equity). This is configurable.

*This model accepts additional fields of type Any.*

## Enumeration

`RiskProfile2`

## Fields

| Name |
|  --- |
| `CONSERVATIVE` |
| `MODERATE` |
| `AGGRESSIVE` |

## Example

```python
from goeapi.models.risk_profile_2 import RiskProfile2

risk_profile_2 = RiskProfile2.AGGRESSIVE
```

