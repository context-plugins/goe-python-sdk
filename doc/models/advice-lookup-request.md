
# Advice Lookup Request

*This model accepts additional fields of type Any.*

## Structure

`AdviceLookupRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `advice_id` | `str` | Required | The system-generated unique identifier for a historical API request. Supplying this value retrieves the details of the corresponding advice interaction, including the request payload, response, user email, API endpoint, and timestamp. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.advice_lookup_request import AdviceLookupRequest

advice_lookup_request = AdviceLookupRequest(
    advice_id='e0623d22d2d843ee94634438e64375b4',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

