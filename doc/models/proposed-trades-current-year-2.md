
# Proposed Trades Current Year 2

Details of trade as of today i.e., current date & end of the year

*This model accepts additional fields of type Any.*

## Structure

`ProposedTradesCurrentYear2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `end_of_current_year` | [`EndOfCurrentYear`](../../doc/models/end-of-current-year.md) | Required | - |
| `today` | [`Today`](../../doc/models/today.md) | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.account_response import AccountResponse
from goeapi.models.end_of_current_year import EndOfCurrentYear
from goeapi.models.proposed_trades_current_year_2 import ProposedTradesCurrentYear2
from goeapi.models.today import Today
from goeapi.models.trade import Trade

proposed_trades_current_year_2 = ProposedTradesCurrentYear2(
    end_of_current_year=EndOfCurrentYear(
        accounts=[
            AccountResponse(
                account_id='T',
                trades=[
                    Trade(
                        direction='S',
                        symbol='CASH',
                        cusip='cusip4',
                        quantity=29178,
                        amount=10748.399065,
                        trade_type=None,
                        additional_properties={
                            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                        }
                    )
                ],
                additional_properties={
                    'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                }
            )
        ],
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    today=Today(
        accounts=[
            AccountResponse(
                account_id='T',
                trades=[
                    Trade(
                        direction='S',
                        symbol='CASH',
                        cusip='cusip4',
                        quantity=29178,
                        amount=10748.399065,
                        trade_type=None,
                        additional_properties={
                            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                        }
                    )
                ],
                additional_properties={
                    'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                }
            )
        ],
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

