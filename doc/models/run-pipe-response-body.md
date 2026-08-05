
# Run Pipe Response Body

*This model accepts additional fields of type Any.*

## Structure

`RunPipeResponseBody`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `analysis_report` | [`RunPipeAnalysisReport1`](../../doc/models/run-pipe-analysis-report-1.md) | Required | Captures various important recommendations and outputs from the GOE engine. |
| `path_report` | [`PathReport1`](../../doc/models/path-report-1.md) | Required | Captures lookforward portfolio and wealth paths as calcualted by the GOE engine. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.path_report_1 import PathReport1
from goeapi.models.run_pipe_analysis_report_1 import RunPipeAnalysisReport1
from goeapi.models.run_pipe_response_body import RunPipeResponseBody
from goeapi.models.wealth_path_2 import WealthPath2

run_pipe_response_body = RunPipeResponseBody(
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
)
```

