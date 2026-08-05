
# Goal Calculator Response Body Model

*This model accepts additional fields of type Any.*

## Structure

`GoalCalculatorResponseBodyModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `goal_amt` | `float` | Required | - |
| `infusions` | `List[float]` | Required | - |
| `cashflow` | [`List[CashFlowDict]`](../../doc/models/cash-flow-dict.md) | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.goal_calculator_response_body_model import GoalCalculatorResponseBodyModel

goal_calculator_response_body_model = GoalCalculatorResponseBodyModel(
    goal_amt=52.2,
    infusions=[
        0,
        4000,
        4000,
        -477921,
        -477921
    ],
    cashflow=[
        None
    ],
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

