
# Draft Entry

*This model accepts additional fields of type Any.*

## Structure

`DraftEntry`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `advice_id` | str \| List[str] | Required | This is a container for any-of cases. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.draft_entry import DraftEntry

draft_entry = DraftEntry(
    advice_id='String7',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

