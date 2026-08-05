
# Policy Details

*This model accepts additional fields of type Any.*

## Structure

`PolicyDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `participant_type` | `str` | Optional | This captures the underlying end-investor/participant type. |
| `call_type` | `str` | Optional | This captures the underlying end investor/call type |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.policy_details import PolicyDetails

policy_details = PolicyDetails(
    participant_type='P12345',
    call_type='Conversion',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

