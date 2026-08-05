
# Cashflow Object Type

Mandatory if cashflow list if defined.

*This model accepts additional fields of type Any.*

## Enumeration

`CashflowObjectType`

## Fields

| Name |
|  --- |
| `CONTRIBUTION` |
| `GOAL` |
| `OTHER_INCOME` |
| `SOCIAL_SECURITY` |
| `BEQUEST` |

## Example

```python
from goeapi.models.cashflow_object_type import CashflowObjectType

cashflow_object_type = CashflowObjectType.SOCIAL_SECURITY
```

