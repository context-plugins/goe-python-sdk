
# Bulk Upsert Advice

*This model accepts additional fields of type Any.*

## Structure

`BulkUpsertAdvice`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `str` | Required | Provides the status of the response. |
| `updated` | `List[str]` | Required | Provides a list of Advice IDs that were successfully passed. |
| `failed` | `List[str]` | Required | Provides a list of Advice IDs that were not passed. |
| `invalid_ids` | `List[str]` | Required | Provides a list of Advice IDs that are invalid, and not passed. |
| `total_processed` | `int` | Required | Provides a count of how many Advice IDs were passed. |
| `chunks_processed` | `int` | Optional | Provides a count of how many Advice ID chunks were passed.<br><br>**Default**: `0` |
| `message` | `str` | Required | Provides the response message. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.bulk_upsert_advice import BulkUpsertAdvice

bulk_upsert_advice = BulkUpsertAdvice(
    status='status2',
    updated=[
        'updated3',
        'updated2'
    ],
    failed=[
        'failed4'
    ],
    invalid_ids=[
        'invalid_ids2'
    ],
    total_processed=6,
    message='message0',
    chunks_processed=0,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

