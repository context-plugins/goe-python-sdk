
# Ews Account Infusion Item

*This model accepts additional fields of type Any.*

## Structure

`EwsAccountInfusionItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `date` | `str` | Required | Date at which the contribution happens. |
| `value` | `float` | Required | Infusion value for the given date.<br><br>**Constraints**: `>= 0` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.ews_account_infusion_item import EwsAccountInfusionItem

ews_account_infusion_item = EwsAccountInfusionItem(
    date='date8',
    value=125.34,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

