
# Refresh Token Input Model

*This model accepts additional fields of type Any.*

## Structure

`RefreshTokenInputModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `refresh_token` | `str` | Required | Refresh Token. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.refresh_token_input_model import RefreshTokenInputModel

refresh_token_input_model = RefreshTokenInputModel(
    refresh_token='HEpb6yNYH68XTFING3a_RkqLHOgFosQv5-7W0_So3VE',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

