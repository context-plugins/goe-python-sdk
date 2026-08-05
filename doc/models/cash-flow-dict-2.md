
# Cash Flow Dict 2

*This model accepts additional fields of type Any.*

## Structure

`CashFlowDict2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mtype` | [`CashflowObjectType`](../../doc/models/cashflow-object-type.md) | Required | Mandatory if cashflow list if defined. |
| `amount` | `float` | Required | Mandatory if cashflow list if defined.<br><br>**Constraints**: `>= 0` |
| `start_date` | `str` | Optional | Mandatory for all types if cashflow list if defined. Optional only when type is BEQUEST. Date in the format of "dd-mm-yyyy". For Bequest, if startDate and endDate are passed, they have to be same. |
| `end_date` | `str` | Optional | Mandatory for "CONTRIBUTION". For the remaining four, it is optional. Date in the format of "dd-mm-yyyy". When not passed, the end date of parent object will be considered in the algo. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.cash_flow_dict_2 import CashFlowDict2
from goeapi.models.cashflow_object_type import CashflowObjectType

cash_flow_dict_2 = CashFlowDict2(
    mtype=CashflowObjectType.SOCIAL_SECURITY,
    amount=187.34,
    start_date='startDate2',
    end_date='endDate4',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

