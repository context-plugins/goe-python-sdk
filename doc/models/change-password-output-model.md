
# Change Password Output Model

*This model accepts additional fields of type Any.*

## Structure

`ChangePasswordOutputModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `success` | `bool` | Required | Returns ‘true’ when successful and ‘false’ when failed. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.change_password_output_model import ChangePasswordOutputModel

change_password_output_model = ChangePasswordOutputModel(
    success=False,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

