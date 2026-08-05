
# Advice Lookup Response

*This model accepts additional fields of type Any.*

## Structure

`AdviceLookupResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status_code` | `int` | Required | Status code for the response. |
| `message` | `str` | Required | Returns appropriate message for each status code. |
| `body` | [`HistoricalAuditRecord`](../../doc/models/historical-audit-record.md) | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.advice_lookup_response import AdviceLookupResponse
from goeapi.models.historical_audit_record import HistoricalAuditRecord

advice_lookup_response = AdviceLookupResponse(
    status_code=196,
    message='message2',
    body=HistoricalAuditRecord(
        advice_id='adviceId6',
        created_at='createdAt0',
        payload=jsonpickle.decode('{"key1":"val1","key2":"val2"}'),
        response=jsonpickle.decode('{"key1":"val1","key2":"val2"}'),
        user_email='userEmail4',
        api_name='apiName6',
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

