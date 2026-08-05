
# Value

*This model accepts additional fields of type Any.*

## Structure

`Value`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `year` | `int` | Required | - |
| `rate` | `float` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.value import Value

value = Value(
    year=62,
    rate=5.73354,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

