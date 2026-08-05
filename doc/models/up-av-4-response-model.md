
# Up Av 4 Response Model

*This model accepts additional fields of type Any.*

## Structure

`UpAv4ResponseModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status_code` | `int` | Required | - |
| `message` | `str` | Required | - |
| `body` | [`UpaResponseBody`](../../doc/models/upa-response-body.md) | Required | - |
| `advice_id` | `str` | Required | Unique identifier for each response. The ID can be used as an input in the /api/goe-api/advice-status API request. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.cashflow_recommendation_1 import CashflowRecommendation1
from goeapi.models.priority_3 import Priority3
from goeapi.models.up_av_4_response_model import UpAv4ResponseModel
from goeapi.models.upa_analysis_report_1 import UpaAnalysisReport1
from goeapi.models.upa_analysis_report_mod_1 import UpaAnalysisReportMod1
from goeapi.models.upa_goal_response import UpaGoalResponse
from goeapi.models.upa_path_report_1 import UpaPathReport1
from goeapi.models.upa_path_report_mod_1 import UpaPathReportMod1
from goeapi.models.upa_response_body import UpaResponseBody

up_av_4_response_model = UpAv4ResponseModel(
    status_code=10,
    message='message4',
    body=UpaResponseBody(
        analysis_report=UpaAnalysisReport1(
            current_goal_probability=10000,
            recommended_portfolio_id=6,
            meet_goal_priority=False,
            is_goal_realistic=False,
            one_time_top_up=38859,
            cashflow_recommendation=CashflowRecommendation1(
                cash_flow_monthly=None,
                cash_flow_yearly=2503,
                start_date='01-01-2022',
                end_date='01-01-2036',
                new_plan_prob=0.85,
                additional_properties={
                    'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                }
            ),
            bankruptcy_msg='NA',
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        path_report=UpaPathReport1(
            portfolio_path=[
                123,
                124,
                125
            ],
            wealth_path=[
                195.65,
                195.66
            ],
            worst_case_path=[
                182.68
            ],
            best_case_path=[
                238.1,
                238.09,
                238.08
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        analysis_report_mod=UpaAnalysisReportMod1(
            current_goal_probability=10000,
            recommended_portfolio_id=6,
            meet_goal_priority=False,
            is_goal_realistic=False,
            one_time_top_up=38859,
            cashflow_recommendation=CashflowRecommendation1(
                cash_flow_monthly=None,
                cash_flow_yearly=2503,
                start_date='01-01-2022',
                end_date='01-01-2036',
                new_plan_prob=0.85,
                additional_properties={
                    'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                }
            ),
            bankruptcy_msg='NA',
            goals_response=[
                UpaGoalResponse(
                    goal_id='Goal1',
                    goal_amt=[
                        179.05
                    ],
                    start_date='01-01-2021',
                    end_date='01-01-2031',
                    priority=Priority3.DREAM,
                    modified_goal_amt=[
                        72.68,
                        72.69
                    ],
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            comments='To meet all goals optimally as per their assigned priorities Goal1 has been reduced by 100.0%, Goal2 has been reduced by 50.0% of its original value. The allocated portfolio has an 94.316% probability of meeting the modified goals',
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        path_report_mod=UpaPathReportMod1(
            portfolio_path=[
                233,
                234,
                235
            ],
            wealth_path=[
                223.59
            ],
            worst_case_path=[
                210.62,
                210.63,
                210.64
            ],
            best_case_path=[
                198.16,
                198.17,
                198.18
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    advice_id='adviceID4',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

