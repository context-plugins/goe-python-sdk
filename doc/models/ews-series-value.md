
# Ews Series Value

*This model accepts additional fields of type Any.*

## Structure

`EwsSeriesValue`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `value` | `float` | Required | Cashflow amount<br><br>**Constraints**: `>= 0` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.ews_series_value import EwsSeriesValue

ews_series_value = EwsSeriesValue(
    value=120.72,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

