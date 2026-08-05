
# Today Trades Info

*This model accepts additional fields of type Any.*

## Structure

`TodayTradesInfo`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accounts` | [`List[GoeToAccountResponse]`](../../doc/models/goe-to-account-response.md) | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.goe_to_account_response import GoeToAccountResponse
from goeapi.models.today_trades_info import TodayTradesInfo
from goeapi.models.trade_info import TradeInfo

today_trades_info = TodayTradesInfo(
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
)
```

