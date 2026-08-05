
# Risk Profile 6

Defines the user’s risk profile. Note that Risk Profiles are mapped to portfolio access. For example, a Conservative investor has access to portfolios 1-8 (or 50% Equity) while an Aggressive investor has access to all 16 portfolios (up to 90% Equity).             On a default basis, GOE is configured for three Risk Profile levels, but it can be customized for up to five levels.

*This model accepts additional fields of type Any.*

## Enumeration

`RiskProfile6`

## Fields

| Name |
|  --- |
| `CONSERVATIVE` |
| `MODERATE` |
| `AGGRESSIVE` |

## Example

```python
from goeapi.models.risk_profile_6 import RiskProfile6

risk_profile_6 = RiskProfile6.MODERATE
```

