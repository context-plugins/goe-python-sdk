
# Today

*This model accepts additional fields of type Any.*

## Structure

`Today`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accounts` | [`List[AccountResponse]`](../../doc/models/account-response.md) | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.account_response import AccountResponse
from goeapi.models.today import Today
from goeapi.models.trade import Trade

today = Today(
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
)
```

