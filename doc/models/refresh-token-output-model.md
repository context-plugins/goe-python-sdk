
# Refresh Token Output Model

*This model accepts additional fields of type Any.*

## Structure

`RefreshTokenOutputModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `authentication_result` | [`AuthenticationResult`](../../doc/models/authentication-result.md) | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.authentication_result import AuthenticationResult
from goeapi.models.refresh_token_output_model import RefreshTokenOutputModel

refresh_token_output_model = RefreshTokenOutputModel(
    authentication_result=AuthenticationResult(
        access_token='AccessToken8',
        expires_in=78,
        id_token='IdToken0',
        refresh_token='RefreshToken4',
        scope='Scope8',
        token_type='TokenType0',
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

