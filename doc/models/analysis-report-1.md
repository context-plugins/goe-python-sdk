
# Analysis Report 1

This section gives details of the GOE run for the original plan.

*This model accepts additional fields of type Any.*

## Structure

`AnalysisReport1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bankruptcy_msg` | `str` | Required | Message flagging an expected bankruptcy (goal running out of money) in any year.<br>                    Note: <br>                    If ‘NA’, bankruptcy is unlikely to happen during the goal tenure.                     In bankruptcy cases, response would be of the format:                      There is more than 75% probability of going bankrupt after year 10 |
| `current_goal_probability` | `float` | Required | GOE’s estimated probability to achieve the goal target wealth.<br>                    Note: <br>                    To be displayed as 63% (rounded with no decimals) |
| `expected_taxes_for_current_year` | [`ExpectedTaxesForCurrentYear2`](../../doc/models/expected-taxes-for-current-year-2.md) | Required | Details of the taxes as received from LifeYield.<br>                    Note:<br>                    The taxes pertain to accounts that are under GOE’s discretion & are computed, in this dictionary, only for current financial year. |
| `is_goal_realistic` | `bool` | Required | To understand if the goal probability is more                     than 35% (This is a configurable field).<br>                    Note: <br>                    If ‘false’, goal is unrealistic. |
| `meet_goal_priority` | `bool` | Required | Checks if goal probability is more than the                     target probability corresponding to the goal                     priority – Target probabilities for all goal                     priorities (Need, Want, Wish and Dream, Desire) are                     set in the GOE config.  <br>                    Note: <br>                    If ‘true’, goal                     probability achieves the                     target probability. <br>                    If ‘false’, goal probability                     falls short of the target                     probability. |
| `one_time_top_up` | `Any` | Required | Recommendations based on available accounts. <br>                     Note: <br>                     The retirement accounts for MVP are of the variety “401k”. <br>                     The max contribution amount recommendation is based solely on accounts available to GOE. |
| `proposed_trades_current_year` | [`ProposedTradesCurrentYear2`](../../doc/models/proposed-trades-current-year-2.md) | Required | Details of trade as of today i.e., current date & end of the year |
| `recommended_portfolio_id` | `int` | Required | GOE’s current recommended portfolio index. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.account_response import AccountResponse
from goeapi.models.analysis_report_1 import AnalysisReport1
from goeapi.models.end_of_current_year import EndOfCurrentYear
from goeapi.models.expected_taxes_for_current_year_2 import ExpectedTaxesForCurrentYear2
from goeapi.models.proposed_trades_current_year_2 import ProposedTradesCurrentYear2
from goeapi.models.today import Today
from goeapi.models.trade import Trade

analysis_report_1 = AnalysisReport1(
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
)
```

