
# Advice Payload

*This model accepts additional fields of type Any.*

## Structure

`AdvicePayload`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `completely_traded` | [`List[CompletelyTradedEntry]`](../../doc/models/completely-traded-entry.md) | Optional | Provides a list of Advice IDs and the corresponding timestamp of all API responses that have been fully traded,             where the entire portfolio recommendation was implemented. |
| `partially_traded` | [`List[PartiallyTradedEntry]`](../../doc/models/partially-traded-entry.md) | Optional | Provides a list of Advice IDs and the corresponding timestamp of all API responses that have been partially traded. |
| `final_proposal` | [`List[FinalProposalEntry]`](../../doc/models/final-proposal-entry.md) | Optional | Provides a list of Advice IDs and the corresponding timestamp of all API responses that have been approved, but not yet traded. |
| `draft` | [`List[DraftEntry]`](../../doc/models/draft-entry.md) | Optional | Provides a list of Advice IDs of all API responses that have not been approved or traded. |
| `test` | [`List[TestEntry]`](../../doc/models/test-entry.md) | Optional | Provides a list of Advice IDs and the corresponding timestamp of all API responses that have been used with test data.             Advice IDs provided in this list were not used in real world situations, purely for testing purposes. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.advice_payload import AdvicePayload
from goeapi.models.completely_traded_entry import CompletelyTradedEntry
from goeapi.models.draft_entry import DraftEntry
from goeapi.models.partially_traded_entry import PartiallyTradedEntry
from goeapi.models.test_entry import TestEntry

advice_payload = AdvicePayload(
    completely_traded=[
        CompletelyTradedEntry(
            advice_id=[
                '68cb7e2eb6434ec5aeb0e7d721e48e9e'
            ],
            date='20250722T145113Z',
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        CompletelyTradedEntry(
            advice_id=[
                'd9b057db6c3c4814968edfa1708f3924',
                '5ede8559226b4b688c654aac75a59a12',
                'ca646c91dcee4ff58ce2a989f0240451'
            ],
            date='20250722T145113Z',
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    partially_traded=[
        None,
        PartiallyTradedEntry(
            advice_id=None,
            date=None
        )
    ],
    final_proposal=[
        None
    ],
    draft=[
        DraftEntry(
            advice_id='0b0d0b9afa5940a188ff6c1f65b887f9',
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    test=[
        TestEntry(
            advice_id=[
                '4c5c903f955d402f9cb0aa5029c60267',
                'test999-888888'
            ],
            date='20251130T145113Z',
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

