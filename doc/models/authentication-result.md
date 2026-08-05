
# Authentication Result

*This model accepts additional fields of type Any.*

## Structure

`AuthenticationResult`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `access_token` | `str` | Required | - |
| `expires_in` | `int` | Required | - |
| `id_token` | `str` | Required | - |
| `refresh_token` | `str` | Required | - |
| `scope` | `str` | Required | - |
| `token_type` | `str` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.authentication_result import AuthenticationResult

authentication_result = AuthenticationResult(
    access_token='AccessToken8',
    expires_in=210,
    id_token='IdToken0',
    refresh_token='RefreshToken4',
    scope='Scope8',
    token_type='TokenType0',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

