
# Goe to Analysis Report 2

This section gives details of the GOE run for the original plan.

*This model accepts additional fields of type Any.*

## Structure

`GoeToAnalysisReport2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bankruptcy_msg` | `str` | Required | Message flagging an expected bankruptcy (goal running out of money) in any year. <br>                    Note:  <br>                    If ‘NA’, bankruptcy is unlikely to happen during the goal tenure.                     In bankruptcy cases, response would be of the format: <br>                    There is more than 75% probability of going bankrupt after year 10 |
| `current_goal_probability` | `float` | Required | GOE’s estimated probability to achieve the goal target wealth. <br>                    Note:  <br>                    To be displayed as 63% (rounded with no decimals) |
| `expected_taxes_for_current_year` | [`GoeToExpectedTaxesForCurrentYear2`](../../doc/models/goe-to-expected-taxes-for-current-year-2.md) | Required | Details of the taxes as received from LifeYield. <br>                    Note: <br>                    The taxes pertain to accounts that are under GOE’s discretion & are computed, in this dictionary, only for current financial year. |
| `is_goal_realistic` | `bool` | Required | To understand if the goal probability is more                     than 35% (This is a configurable field). <br>                    Note: If ‘false’, goal is                     unrealistic. |
| `meet_goal_priority` | `bool` | Required | Checks if goal probability is more than the                     target probability corresponding to the goal                     priority – Target probabilities for all goal                     priorities (Need, Want, Wish and Dream, Desire) are                     set in the GOE config. <br>                     Note: If ‘true’, goal                     probability achieves the                     target probability.                     If ‘false’, goal probability                     falls short of the target                     probability. |
| `one_time_top_up` | `Any` | Required | Recommendations based on available accounts. Two objectives of recommendations: <br>                    1.	Ensure the probability of withdrawal from the taxable account is greater than the priority of the goal (pre-59.5Y). This is applicable if the user has taxable account with TDA / Roth account. <br>                    2.	Add money to the retirement accounts if the current threshold for contributing to retirement accounts is not met. |
| `proposed_trades_current_year` | [`ProposedTradesCurrentYearInfo2`](../../doc/models/proposed-trades-current-year-info-2.md) | Required | Details of trade as of today i.e., current date & end of the year |
| `recommended_portfolio_id` | `int` | Required | GOE’s current recommended portfolio index. <br>                    Note: Can be between 1                     to 16. Also subject to                     investor’s risk profile: for                     example, conservative                     investors have access to                    1-8 portfolios while                     Aggressive investors have                     access to 1-16. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.goe_to_account_response import GoeToAccountResponse
from goeapi.models.goe_to_analysis_report_2 import GoeToAnalysisReport2
from goeapi.models.goe_to_end_of_current_year import GoeToEndOfCurrentYear
from goeapi.models.goe_to_expected_taxes_for_current_year_2 import GoeToExpectedTaxesForCurrentYear2
from goeapi.models.proposed_trades_current_year_info_2 import ProposedTradesCurrentYearInfo2
from goeapi.models.today_trades_info import TodayTradesInfo
from goeapi.models.trade_info import TradeInfo

goe_to_analysis_report_2 = GoeToAnalysisReport2(
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
)
```

