
# Internal Server Message 1 Exception

*This model accepts additional fields of type Any.*

## Structure

`InternalServerMessage1Exception`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `str` | Required | error message |
| `status_code` | `int` | Required | statuscode |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
try:
    # make the API call
except InternalServerMessage1Exception as e:
    print(e)
except ApiException as e:
    print(e)
```

