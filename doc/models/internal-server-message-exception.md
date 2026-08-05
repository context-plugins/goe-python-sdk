
# Internal Server Message Exception

*This model accepts additional fields of type Any.*

## Structure

`InternalServerMessageException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `str` | Required | message |
| `status_code` | `int` | Required | statuscode |
| `body` | `str` | Required | body |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
try:
    # make the API call
except InternalServerMessageException as e:
    print(e)
except ApiException as e:
    print(e)
```

