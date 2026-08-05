
# Internal Server Message General Exception

*This model accepts additional fields of type Any.*

## Structure

`InternalServerMessageGeneralException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `str` | Required | message |
| `status_code` | `int` | Required | statuscode |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
try:
    # make the API call
except InternalServerMessageGeneralException as e:
    print(e)
except ApiException as e:
    print(e)
```

