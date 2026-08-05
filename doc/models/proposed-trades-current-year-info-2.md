
# Proposed Trades Current Year Info 2

Details of trade as of today i.e., current date & end of the year

*This model accepts additional fields of type Any.*

## Structure

`ProposedTradesCurrentYearInfo2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `end_of_current_year` | [`GoeToEndOfCurrentYear`](../../doc/models/goe-to-end-of-current-year.md) | Required | - |
| `today` | [`TodayTradesInfo`](../../doc/models/today-trades-info.md) | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.goe_to_account_response import GoeToAccountResponse
from goeapi.models.goe_to_end_of_current_year import GoeToEndOfCurrentYear
from goeapi.models.proposed_trades_current_year_info_2 import ProposedTradesCurrentYearInfo2
from goeapi.models.today_trades_info import TodayTradesInfo
from goeapi.models.trade_info import TradeInfo

proposed_trades_current_year_info_2 = ProposedTradesCurrentYearInfo2(
    end_of_current_year=GoeToEndOfCurrentYear(
        accounts=[
            GoeToAccountResponse(
                account_id='T',
                trades=[
                    TradeInfo(
                        direction='S',
                        symbol='CASH',
                        cusip='cusip4',
                        quantity=29178,
                        amount=10748.399065,
                        phase='phase2',
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
    today=TodayTradesInfo(
        accounts=[
            GoeToAccountResponse(
                account_id='T',
                trades=[
                    TradeInfo(
                        direction='S',
                        symbol='CASH',
                        cusip='cusip4',
                        quantity=29178,
                        amount=10748.399065,
                        phase='phase2',
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

