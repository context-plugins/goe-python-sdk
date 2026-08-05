
# Refresh Token Status Exception

*This model accepts additional fields of type Any.*

## Structure

`RefreshTokenStatusException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | `str` | Required | - |
| `message` | `str` | Required | message |
| `status_code` | `int` | Required | status code |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
try:
    # make the API call
except RefreshTokenStatusException as e:
    print(e)
except ApiException as e:
    print(e)
```

