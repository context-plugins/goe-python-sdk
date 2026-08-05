
# Annuity Price

*This model accepts additional fields of type Any.*

## Structure

`AnnuityPrice`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `age` | `int` | Required | - |
| `value` | [`List[Value]`](../../doc/models/value.md) | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.annuity_price import AnnuityPrice
from goeapi.models.value import Value

annuity_price = AnnuityPrice(
    age=50,
    value=[
        Value(
            year=62,
            rate=5.73354,
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

