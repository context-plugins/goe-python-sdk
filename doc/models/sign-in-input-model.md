
# Sign In Input Model

*This model accepts additional fields of type Any.*

## Structure

`SignInInputModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `str` | Required | Email to login. |
| `password` | `str` | Required | Password to login. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.sign_in_input_model import SignInInputModel

sign_in_input_model = SignInInputModel(
    email='abc@abc.com',
    password='Gpattm@#124',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

