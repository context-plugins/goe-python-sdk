
# Change Password Input Model

*This model accepts additional fields of type Any.*

## Structure

`ChangePasswordInputModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `str` | Required | Email of the user for change password. |
| `old_password` | `str` | Required | oldPassword for password change. |
| `new_password` | `str` | Required | newPassword which will be used from now. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.change_password_input_model import ChangePasswordInputModel

change_password_input_model = ChangePasswordInputModel(
    email='abc@abc.com',
    old_password='oldpass@#&7',
    new_password='newpass@#&7',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

