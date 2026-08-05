
# Run Pipe Response Model V4

*This model accepts additional fields of type Any.*

## Structure

`RunPipeResponseModelV4`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status_code` | `int` | Required | - |
| `message` | `str` | Required | - |
| `body` | [`RunPipeResponseBody`](../../doc/models/run-pipe-response-body.md) | Required | - |
| `advice_id` | `str` | Required | Unique identifier for each response. The ID can be used as an input in the /api/goe-api/advice-status API request. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.path_report_1 import PathReport1
from goeapi.models.run_pipe_analysis_report_1 import RunPipeAnalysisReport1
from goeapi.models.run_pipe_response_body import RunPipeResponseBody
from goeapi.models.run_pipe_response_model_v_4 import RunPipeResponseModelV4
from goeapi.models.wealth_path_2 import WealthPath2

run_pipe_response_model_v_4 = RunPipeResponseModelV4(
    status_code=172,
    message='message8',
    body=RunPipeResponseBody(
        analysis_report=RunPipeAnalysisReport1(
            current_goal_probability=0.99,
            recommended_portfolio_id=36,
            meet_goal_priority=False,
            is_goal_realistic=False,
            one_time_top_up=126.44,
            yearly_top_up_accumulation=100.16,
            monthly_top_up_accumulation=198.96,
            yearly_top_up_decumulation=117.08,
            monthly_top_up_decumulation=32.26,
            recommended_tenure='recommendedTenure6',
            bankruptcy_msg='bankruptcyMsg4',
            message='message2',
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        path_report=PathReport1(
            portfolio_path=[
                219,
                220
            ],
            wealth_path=WealthPath2(
                default=[
                    94.4
                ],
                pessimistic=[
                    35.74,
                    35.75,
                    35.76
                ],
                optimistic=[
                    210.96,
                    210.97
                ],
                default_percentile='defaultPercentile6',
                pessimistic_percentile='pessimisticPercentile4',
                optimistic_percentile='optimisticPercentile6',
                additional_properties={
                    'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                }
            ),
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    advice_id='adviceID6',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

