
# Validation Message One Exception

*This model accepts additional fields of type Any.*

## Structure

`ValidationMessageOneException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status_code` | `int` | Required | statuscode |
| `message` | `str` | Required | Validation Error |
| `body` | `str` | Required | Validation error message |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
try:
    # make the API call
except ValidationMessageOneException as e:
    print(e)
except ApiException as e:
    print(e)
```

