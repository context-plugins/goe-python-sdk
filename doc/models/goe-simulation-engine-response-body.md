
# Goe Simulation Engine Response Body

*This model accepts additional fields of type Any.*

## Structure

`GoeSimulationEngineResponseBody`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `analysis_report` | [`AnalysisReport1`](../../doc/models/analysis-report-1.md) | Required | This section gives details of the GOE run for the original plan. |
| `analysis_report_mod` | `str` | Required | In the event the original plan doesn’t meetnthe desired probability (in line with the priority),                     the plan is modified by dropping less important goal – denoted by lower priority.                     This is not applicable for the 1.0 version of GOE-SOFT. |
| `path_report` | [`PathReportSimulationEngine2`](../../doc/models/path-report-simulation-engine-2.md) | Required | Forward looking estimates of likely portfolios,                     wealth, withdrawals, and taxes |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.account_response import AccountResponse
from goeapi.models.analysis_report_1 import AnalysisReport1
from goeapi.models.end_of_current_year import EndOfCurrentYear
from goeapi.models.expected_taxes_for_current_year_2 import ExpectedTaxesForCurrentYear2
from goeapi.models.goe_simulation_engine_response_body import GoeSimulationEngineResponseBody
from goeapi.models.path_report_simulation_engine_2 import PathReportSimulationEngine2
from goeapi.models.proposed_trades_current_year_2 import ProposedTradesCurrentYear2
from goeapi.models.rmd_amount import RmdAmount
from goeapi.models.today import Today
from goeapi.models.trade import Trade

goe_simulation_engine_response_body = GoeSimulationEngineResponseBody(
    analysis_report=AnalysisReport1(
        bankruptcy_msg='NA',
        current_goal_probability=0.6504,
        expected_taxes_for_current_year=ExpectedTaxesForCurrentYear2(
            federal_ordinary_income_tax_liability=0,
            federal_qualified_dividends_tax_liability=0,
            federal_capital_gains_rebalancing_liability=0,
            federal_capital_gains_withdrawal_liability=0,
            federal_early_distribution_penalty=0.15,
            federal_tax_due_to_rmd=0.15,
            federal_tax_due_to_social_security=0.15,
            federal_total_tax_liability=0.15,
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        is_goal_realistic=False,
        meet_goal_priority=False,
        one_time_top_up=jsonpickle.decode('{"D":0.0,"F":30000.0,"T":121043}'),
        proposed_trades_current_year=ProposedTradesCurrentYear2(
            end_of_current_year=EndOfCurrentYear(
                accounts=[
                    AccountResponse(
                        account_id='T',
                        trades=[
                            Trade(
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
                        ],
                        additional_properties={
                            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                        }
                    )
                ],
                additional_properties={
                    'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                }
            ),
            today=Today(
                accounts=[
                    AccountResponse(
                        account_id='T',
                        trades=[
                            Trade(
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
                        ],
                        additional_properties={
                            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                        }
                    )
                ],
                additional_properties={
                    'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                }
            ),
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        recommended_portfolio_id=10,
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    analysis_report_mod=None,
    path_report=PathReportSimulationEngine2(
        early_withdrawal_penalty=0,
        ending_wealth=jsonpickle.decode('{"expected":221160.0,"optimistic":240110.0,"pessimistic":204004.0}'),
        expected_tax_amount=0,
        goal_amount=121.5,
        period=2,
        portfolio_id=16,
        rmd_amount=[
            RmdAmount(
                amount=127.8,
                member_id='memberId8',
                additional_properties={
                    'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                }
            )
        ],
        social_security_amount=[
            RmdAmount(
                amount=87.4,
                member_id='memberId8',
                additional_properties={
                    'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                }
            )
        ],
        withdrawal_amount=jsonpickle.decode('{"D":0.0,"F":0.0,"T":0.0}'),
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

