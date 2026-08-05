
# Message Exception

*This model accepts additional fields of type Any.*

## Structure

`MessageException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `str` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
try:
    # make the API call
except MessageException as e:
    print(e)
except ApiException as e:
    print(e)
```

