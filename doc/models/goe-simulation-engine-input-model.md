
# Goe Simulation Engine Input Model

*This model accepts additional fields of type Any.*

## Structure

`GoeSimulationEngineInputModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `reallocate` | `bool` | Required | Set as “true” when a newportfolio is needed. |
| `is_new_goal_priority` | `bool` | Optional | If investor/end user changes the goal priority of any of the goals within the plan, in between the re-allocation dates, this is set to ‘true’. <br>                                     For new plans, this needs to be ‘true’. |
| `reallocation_freq` | `str` | Required, Constant | Describes the frequency of re-allocation.<br><br>**Value**: `"yearly"` |
| `current_portfolio_id` | `int` | Required | Displays the current portfolio assigned to a user. For the firsttime user, this should be set as “null”. |
| `curr_date` | `str` | Optional | The date on which GOE-SOFT call is made.<br>             Valid input format is date –‘dd-mm-yyyy’. |
| `risk_profile` | [`RiskProfile3`](../../doc/models/risk-profile-3.md) | Required | Defines the user’s risk profile, which is mapped to one or more portfolios.This is customizable. |
| `compute_social_security` | `bool` | Optional | When set to true computes the social security.                 Mandatory fields (part of memberList) needed for social security are: “DOB”, “currentSalary”, “socialSecurityStartAge”<br><br>**Default**: `False` |
| `use_social_security_for_goals` | `bool` | Optional | When set to “true” uses Social Security to meet the withdrawals.             If set to “false”, and when 'computeSocialSecurity' is set as 'true' - only computes the Social Security but does not use it to fulfil the goals.             In cases social security (post-tax) is greater than the withdrawal amount, the social security is collected into the taxable accounts.             If no taxable accounts are present, SocialSecurity left – after meeting the goals – is ignored.<br><br>**Default**: `False` |
| `cashflow_date` | `str` | Optional | Cashflow date of the goal - this is the date (year is ignored) on which infusions/withdrawals would be realized for the goal.             This parameter is optional.  If not passed or value is null,             the algorithm would consider the first reallocation date as the cashflow date. |
| `is_new_risk_profile` | `bool` | Required | If the risk profile of the investor has changed, this is set to ‘true’.                                                 For first time calls to GOE, this needs to be set to ‘true’. |
| `is_new_investment_tenure` | `bool` | Optional | If investor/end user changes the goal investment tenure after onboarding and before the next immediate re-allocation date,                                     this is set to ‘true’. For first time calls to GOE, this needs to be set to ‘true’. |
| `is_new_goal` | `bool` | Optional | If the end user changes the goal amount / infusions / withdrawals, in between the re-allocation dates,                     this is set to ‘true’. For retirement scenarios, this would be a change in retirement income goal,                     while for a capital accumulation goal, this would be a change in the lumpsum accumulation target.                     For first time calls to GOE, this needs to be set to ‘true’. |
| `infusion_type` | [`InfusionType2`](../../doc/models/infusion-type-2.md) | Required | Defines if the infusions are at the yearly level or monthly level. |
| `cola_rate` | `float` | Optional | Defines the Cost-of-Living Adjustment to be used for Social Security amount computations.             When passed as “null”, this is assumed to be 0%.<br><br>**Default**: `0` |
| `tax_rates` | [`TaxRates2`](../../doc/models/tax-rates-2.md) | Required | Consists of tax rates applicable pre & post-retirement. |
| `household` | [`Household2`](../../doc/models/household-2.md) | Required | contains all information about all the participants within the household.                         For MVP, only a single member is allowed. |
| `accounts` | [`List[Account]`](../../doc/models/account.md) | Required | Details of different accounts associated with unique memberID in the household. |
| `goal_profile_list` | [`List[GoalProfileSimulationEngine]`](../../doc/models/goal-profile-simulation-engine.md) | Required | Details related to the withdrawals associated with the plan where a plan is defined as a collection of goals. |
| `policy` | [`List[PolicyDetails]`](../../doc/models/policy-details.md) | Optional | Contains details about the policy validation associated with the Platform Partner. In this example,             the array includes participantType and callType, however, the dictionary is open and Platform Partners are able to send other fields to define their respective API Policy. |
| `account_held_away` | `bool` | Optional | To be set to True if the account is a held away account |
| `mean_return` | `float` | Optional | Mean return value for the AHA account. Can be set to null or ignored if ‘accountHeldAway’ is set to False |
| `standard_deviation` | `float` | Optional | Standard deviation for the AHA account. Can be set to null or ignored if ‘accountHeldAway’ is set to False |
| `equity_allocation` | `float` | Optional | The Equity '%' for the AHA account. If this value is provided, the mean and standard deviation is mapped to the GOE managed portfolios. Can be set to null or ignored if ‘accountHeldAway’ is set to False. |
| `lock_expiry_date` | `str` | Optional | The AHA account is considered locked and unavailable for withdrawals till this date. Note that however contributions and RMDs will always be processed. Can be set to null or ignored if ‘accountHeldAway’ is set to False. |
| `target_portfolio` | [`TargetPortfolio2`](../../doc/models/target-portfolio-2.md) | Optional | Target portfolio defines the risk profile for AUA accounts in case user wants to use custom portfolio mode. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.account import Account
from goeapi.models.cashflow_details_2 import CashflowDetails2
from goeapi.models.category import Category
from goeapi.models.goal_profile_simulation_engine import GoalProfileSimulationEngine
from goeapi.models.goe_simulation_engine_input_model import GoeSimulationEngineInputModel
from goeapi.models.household_2 import Household2
from goeapi.models.infusion_type_2 import InfusionType2
from goeapi.models.member import Member
from goeapi.models.member_type_1 import MemberType1
from goeapi.models.priority_2 import Priority2
from goeapi.models.risk_profile_3 import RiskProfile3
from goeapi.models.target_portfolio_2 import TargetPortfolio2
from goeapi.models.tax_rates_2 import TaxRates2

goe_simulation_engine_input_model = GoeSimulationEngineInputModel(
    reallocate=False,
    current_portfolio_id=None,
    risk_profile=RiskProfile3.AGGRESSIVE,
    is_new_risk_profile=False,
    infusion_type=InfusionType2.YEARLY,
    tax_rates=TaxRates2(
        ltcg_pre_retirement=0.15,
        ltcg_post_retirement=0.1,
        etr_pre_retirement=0.15,
        etr_post_retirement=0.2,
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    household=Household2(
        household_id='1',
        member_list=[
            Member(
                member_type=MemberType1.PRIMARY,
                member_id='6c60b501-8957-4393-9323-1dbf6195a00f',
                dob='01-1980',
                current_age=45,
                retirement_age=65,
                current_salary=1,
                social_security_start_age=65,
                tda_balance_for_rmd=74.16,
                rmd_utilized=37.72,
                existing_monthly_social_security_amount=51,
                additional_properties={
                    'lifeExpectancy': jsonpickle.decode('93')
                }
            )
        ],
        state_of_residence='TX',
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    accounts=[
        Account(
            account_id='81571',
            taxability_type='T',
            member_i_ds=[
                '6c60b501-8957-4393-9323-1dbf6195a00f'
            ],
            current_balance=20000,
            current_holdings=[
                Category(
                    category_name='CASH',
                    category_id='10',
                    category_price=1,
                    quantity=20000,
                    cost_basis=20000,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            cashflow_details=CashflowDetails2(
                start_date='02-05-2025',
                end_date='02-05-2045',
                cashflow_amt=[
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0
                ],
                additional_properties={
                    'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                }
            ),
            account_type='accountType0',
            additional_properties={
                'accountHeldAway': jsonpickle.decode('false'),
                'lockExpiry': jsonpickle.decode('{"key1":"val1","key2":"val2"}'),
                'meanReturn': jsonpickle.decode('0.032'),
                'standardDeviation': jsonpickle.decode('0.006')
            }
        )
    ],
    goal_profile_list=[
        GoalProfileSimulationEngine(
            goal_id='39643636326436662d633738642d346230652d386136302d353162363338656162396366',
            start_date='02-05-2045',
            end_date='02-05-2073',
            priority=Priority2.NEED,
            goal_purpose='non-education',
            goal_amt=[
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000,
                60000
            ],
            scenario_type='retirement',
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    is_new_goal_priority=False,
    curr_date='02-05-2025',
    compute_social_security=False,
    use_social_security_for_goals=True,
    cashflow_date='02-05-2025',
    is_new_investment_tenure=False,
    is_new_goal=False,
    cola_rate=0,
    target_portfolio=TargetPortfolio2(
        mean_return=0.032,
        standard_deviation=0.006
    ),
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

