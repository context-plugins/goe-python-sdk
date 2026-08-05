
# Trade

*This model accepts additional fields of type Any.*

## Structure

`Trade`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `direction` | `str` | Required | “S” indicates sale of the asset while “B” indicated purchase |
| `symbol` | `str` | Required | Identifier associated with an asset class |
| `cusip` | `str` | Required | Cusip associated with an asset class |
| `quantity` | `float` | Required | Refers to the amount of sell associated with a trade |
| `amount` | `float` | Required | Refers to the amount of buy associated with a trade |
| `trade_type` | `str` | Required | “Rebalance” refers to trades required to move from one portfolio to another.                     “Withdrawal” refers to trades needed to withdraw a goal amount. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.trade import Trade

trade = Trade(
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
```

