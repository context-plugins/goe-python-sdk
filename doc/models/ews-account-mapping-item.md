
# Ews Account Mapping Item

*This model accepts additional fields of type Any.*

## Structure

`EwsAccountMappingItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `funding_sequence` | `int` | Required | Funding order for the mapped account within a goal.<br><br>**Constraints**: `>= 1` |
| `account_id` | `str` | Required | Unique investment/account identifier used for goal funding. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.ews_account_mapping_item import EwsAccountMappingItem

ews_account_mapping_item = EwsAccountMappingItem(
    funding_sequence=40,
    account_id='accountId4',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

