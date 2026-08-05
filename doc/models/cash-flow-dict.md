
# Cash Flow Dict

*This model accepts additional fields of type Any.*

## Structure

`CashFlowDict`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mtype` | `str` | Required | - |
| `amount` | `float` | Required | - |
| `start_date` | `str` | Optional | - |
| `end_date` | `str` | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.cash_flow_dict import CashFlowDict

cash_flow_dict = CashFlowDict(
    mtype='type4',
    amount=32.86,
    start_date='startDate4',
    end_date='endDate6',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

