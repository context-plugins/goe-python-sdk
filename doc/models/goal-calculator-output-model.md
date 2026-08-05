
# Goal Calculator Output Model

*This model accepts additional fields of type Any.*

## Structure

`GoalCalculatorOutputModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status_code` | `int` | Required | Status code for the response. |
| `message` | `str` | Required | Returns appropriate message for each status code. |
| `body` | [`GoalCalculatorResponseBodyModel`](../../doc/models/goal-calculator-response-body-model.md) | Required | - |
| `advice_id` | `str` | Required | Unique identifier for each response. The ID can be used as an input in the /api/goe-api/advice-status API request. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.cash_flow_dict import CashFlowDict
from goeapi.models.goal_calculator_output_model import GoalCalculatorOutputModel
from goeapi.models.goal_calculator_response_body_model import GoalCalculatorResponseBodyModel

goal_calculator_output_model = GoalCalculatorOutputModel(
    status_code=200,
    message='Success',
    body=GoalCalculatorResponseBodyModel(
        goal_amt=20.9,
        infusions=[
            0,
            4000,
            4000,
            -477921,
            -477921
        ],
        cashflow=[
            None,
            CashFlowDict(
                mtype=None,
                amount=None
            ),
            CashFlowDict(
                mtype=None,
                amount=None
            )
        ],
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    advice_id='adviceID2',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

