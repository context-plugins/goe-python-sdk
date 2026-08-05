
# Final Proposal Entry

*This model accepts additional fields of type Any.*

## Structure

`FinalProposalEntry`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `advice_id` | str \| List[str] | Required | This is a container for any-of cases. |
| `date` | date \| List[date] | Required | This is a container for any-of cases. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import dateutil.parser
import jsonpickle

from goeapi.models.final_proposal_entry import FinalProposalEntry

final_proposal_entry = FinalProposalEntry(
    advice_id='String3',
    date=dateutil.parser.parse('2016-03-13').date(),
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

