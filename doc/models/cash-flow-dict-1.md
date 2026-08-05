
# Cash Flow Dict 1

*This model accepts additional fields of type Any.*

## Structure

`CashFlowDict1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mtype` | [`CashflowObjectType`](../../doc/models/cashflow-object-type.md) | Required | Mandatory if cashflow list if defined. |
| `amount` | `float` | Required | Mandatory if cashflow list if defined. CONTRIBUTION, SOCIAL_SECURITY, OTHER_INCOME are always greater than or equal to zero. BEQUEST and GOAL can be -1 |
| `start_date` | `str` | Optional | Mandatory for all types if cashflow list if defined. Optional only when type is BEQUEST. Date in the format of "dd-mm-yyyy". For Bequest, if startDate and endDate are passed, they have to be same. |
| `end_date` | `str` | Optional | Mandatory for "CONTRIBUTION". For the remaining four, it is optional. Date in the format of "dd-mm-yyyy". When not passed, the end date of parent object will be considered in the algo. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.cash_flow_dict_1 import CashFlowDict1
from goeapi.models.cashflow_object_type import CashflowObjectType

cash_flow_dict_1 = CashFlowDict1(
    mtype=CashflowObjectType.BEQUEST,
    amount=29.22,
    start_date='startDate4',
    end_date='endDate8',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

