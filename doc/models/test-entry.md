
# Test Entry

*This model accepts additional fields of type Any.*

## Structure

`TestEntry`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `advice_id` | str \| List[str] | Required | This is a container for any-of cases. |
| `date` | str \| List[str] | Required | This is a container for any-of cases. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.test_entry import TestEntry

test_entry = TestEntry(
    advice_id='String7',
    date='String3',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

