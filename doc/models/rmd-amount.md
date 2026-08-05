
# Rmd Amount

*This model accepts additional fields of type Any.*

## Structure

`RmdAmount`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `amount` | `float` | Required | - |
| `member_id` | `str` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.rmd_amount import RmdAmount

rmd_amount = RmdAmount(
    amount=104.64,
    member_id='memberId2',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

