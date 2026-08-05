
# Wealth Splitter Output Model

*This model accepts additional fields of type Any.*

## Structure

`WealthSplitterOutputModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status_code` | `int` | Required | Status code for the response. |
| `message` | `str` | Required | Returns appropriate message for each status code. |
| `body` | `Any` | Required | - |
| `goal_response_list` | [`List[GoalResponseItem]`](../../doc/models/goal-response-item.md) | Required | Optimal wealth split details for all goals |
| `request_type` | `str` | Required | - |
| `advice_id` | `str` | Required | Unique identifier for each response. The ID can be used as an input in the /api/goe-api/advice-status API request. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.goal_response_item import GoalResponseItem
from goeapi.models.wealth_splitter_output_model import WealthSplitterOutputModel

wealth_splitter_output_model = WealthSplitterOutputModel(
    status_code=200,
    message='Success',
    body=jsonpickle.decode('{"key1":"val1","key2":"val2"}'),
    goal_response_list=[
        GoalResponseItem(
            goal_id='Goal1',
            goal='Saving',
            orig_curr_wealth=141412,
            min_initial_needed=1114000,
            wealth_split=1038906,
            shortfall=-75094,
            funded_status='Underfunded',
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    request_type='requestType4',
    advice_id='adviceID2',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

