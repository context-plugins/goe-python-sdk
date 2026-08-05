
# Historical Audit Record

*This model accepts additional fields of type Any.*

## Structure

`HistoricalAuditRecord`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `advice_id` | `str` | Required | Unique identifier for each response. The ID can be used as an input in the /api/goe-api/advice-status API request. |
| `created_at` | `str` | Required | The timestamp indicating when the advice record was created. |
| `user_email` | `str` | Optional | The email address associated with the Platform Partner who made the initial API request. |
| `api_name` | `str` | Optional | The name of the API endpoint that was invoked for the initial API request. |
| `payload` | `Any` | Required | The full request payload provided when the historical API request was made. |
| `response` | `Any` | Required | The response returned by the API for the historical API request. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.historical_audit_record import HistoricalAuditRecord

historical_audit_record = HistoricalAuditRecord(
    advice_id='adviceId0',
    created_at='createdAt6',
    payload=jsonpickle.decode('{"key1":"val1","key2":"val2"}'),
    response=jsonpickle.decode('{"key1":"val1","key2":"val2"}'),
    user_email='userEmail8',
    api_name='apiName2',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

