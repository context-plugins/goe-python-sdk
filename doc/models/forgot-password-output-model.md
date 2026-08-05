
# Forgot Password Output Model

*This model accepts additional fields of type Any.*

## Structure

`ForgotPasswordOutputModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `success` | `bool` | Required | Returns either ‘true’ or ‘false’ |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.forgot_password_output_model import ForgotPasswordOutputModel

forgot_password_output_model = ForgotPasswordOutputModel(
    success=False,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

