
# Forgot Password Input Model

*This model accepts additional fields of type Any.*

## Structure

`ForgotPasswordInputModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `str` | Required | Registered email to recieve password. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.forgot_password_input_model import ForgotPasswordInputModel

forgot_password_input_model = ForgotPasswordInputModel(
    email='abc@abc.com',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

