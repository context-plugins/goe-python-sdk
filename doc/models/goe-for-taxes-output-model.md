
# Goe for Taxes Output Model

*This model accepts additional fields of type Any.*

## Structure

`GoeForTaxesOutputModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status_code` | `int` | Required | Status code for the response. |
| `message` | `str` | Required | Returns appropriate message for each status code. |
| `advice_id` | `str` | Required | Unique identifier for each response. The ID can be used as an input in the /api/goe-api/advice-status API request. |
| `body` | [`GoeForTaxesResponseBody`](../../doc/models/goe-for-taxes-response-body.md) | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.analysis_report_mod_1 import AnalysisReportMod1
from goeapi.models.goals_response import GoalsResponse
from goeapi.models.goe_for_taxes_output_model import GoeForTaxesOutputModel
from goeapi.models.goe_for_taxes_response_body import GoeForTaxesResponseBody
from goeapi.models.goe_to_account_response import GoeToAccountResponse
from goeapi.models.goe_to_analysis_report_2 import GoeToAnalysisReport2
from goeapi.models.goe_to_end_of_current_year import GoeToEndOfCurrentYear
from goeapi.models.goe_to_expected_taxes_for_current_year_2 import GoeToExpectedTaxesForCurrentYear2
from goeapi.models.path_report_goe_for_taxes_2 import PathReportGoeForTaxes2
from goeapi.models.proposed_trades_current_year_info_2 import ProposedTradesCurrentYearInfo2
from goeapi.models.rmd_amount import RmdAmount
from goeapi.models.today_trades_info import TodayTradesInfo
from goeapi.models.trade_info import TradeInfo

goe_for_taxes_output_model = GoeForTaxesOutputModel(
    status_code=200,
    message='Success',
    advice_id='adviceID6',
    body=GoeForTaxesResponseBody(
        analysis_report=GoeToAnalysisReport2(
            bankruptcy_msg='NA',
            current_goal_probability=0.6504,
            expected_taxes_for_current_year=GoeToExpectedTaxesForCurrentYear2(
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
            one_time_top_up=jsonpickle.decode('{"T":135040.0}'),
            proposed_trades_current_year=ProposedTradesCurrentYearInfo2(
                end_of_current_year=GoeToEndOfCurrentYear(
                    accounts=[
                        GoeToAccountResponse(
                            account_id='T',
                            trades=[
                                TradeInfo(
                                    direction='S',
                                    symbol='CASH',
                                    cusip='cusip4',
                                    quantity=29178,
                                    amount=10748.399065,
                                    phase='phase2',
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
                today=TodayTradesInfo(
                    accounts=[
                        GoeToAccountResponse(
                            account_id='T',
                            trades=[
                                TradeInfo(
                                    direction='S',
                                    symbol='CASH',
                                    cusip='cusip4',
                                    quantity=29178,
                                    amount=10748.399065,
                                    phase='phase2',
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
            recommended_portfolio_id=16,
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        analysis_report_mod=AnalysisReportMod1(
            goals_response=[
                GoalsResponse(
                    goal_id='Goal2',
                    goal_amt=[
                        179.05
                    ],
                    start_date='01-12-2023',
                    end_date='30-11-2025',
                    modified_goal_amt=[
                        72.68,
                        72.69
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
        path_report=PathReportGoeForTaxes2(
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
    ),
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

