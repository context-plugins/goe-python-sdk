
# Goe to Account Response

*This model accepts additional fields of type Any.*

## Structure

`GoeToAccountResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_id` | `str` | Required | Identifier of an taxabilityType – as described in the request payload |
| `trades` | [`List[TradeInfo]`](../../doc/models/trade-info.md) | Required | Trades for current date - “today” & end of the current year – “endOfCurrentYear”  <br>                    Note:   <br>                    On current date, the trade type will always be “rebalancing” – if the portfolio is changed.                     For end of the year, the trade type will always be “withdrawal” |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.goe_to_account_response import GoeToAccountResponse
from goeapi.models.trade_info import TradeInfo

goe_to_account_response = GoeToAccountResponse(
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
```

