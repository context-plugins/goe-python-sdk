
# Goe for Taxes Input Model

*This model accepts additional fields of type Any.*

## Structure

`GoeForTaxesInputModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `reallocate` | `bool` | Required | If the client wants GOE to reallocate between the scheduled re-allocation dates, this should be set to ‘true’. |
| `is_new_risk_profile` | `bool` | Required | If the risk profile of the investor has changed, this is set to ‘true’.                                                 For first time calls to GOE, this needs to be set to ‘true’. |
| `is_new_investment_tenure` | `bool` | Required | If investor/end user changes the goal investment tenure after onboarding and before the next immediate re-allocation date,                                     this is set to ‘true’. For first time calls to GOE, this needs to be set to ‘true’. |
| `is_new_goal_priority` | `bool` | Required | If investor/end user changes the goal priority of any of the goals within the plan, in between the re-allocation dates, this is set to ‘true’.                                     For new plans, this needs to be ‘true’. |
| `is_near_term_volatility` | `bool` | Optional | When the near-term volatility indicator flashes, this is set to ‘true’. Currently under development,                                                 shold be set to ‘false’.<br><br>**Default**: `False` |
| `is_new_goal` | `bool` | Required | If the end user changes the goal amount / infusions / withdrawals, in between the re-allocation dates,                     this is set to ‘true’. For retirement scenarios, this would be a change in retirement income goal,                     while for a capital accumulation goal, this would be a change in the lumpsum accumulation target.                     For first time calls to GOE, this needs to be set to ‘true’. |
| `get_path` | `bool` | Required | Shows the forward-looking portfolio path over time. |
| `reallocation_freq` | `str` | Required, Constant | Describes the frequency of re-allocation.<br><br>**Value**: `"yearly"` |
| `current_portfolio_id` | `int` | Required | Displays the current portfolio index that the goal is allocated to;                         if GOE is getting executed for the first time, it should be null. |
| `curr_date` | `str` | Optional | This is an optional parameter that can be used to simulate the current date to be the specified value.                         GOE will process the request as if you are making the API call on the specified date. If not passed,                             the current system date will be used as the current date. Valid input format is date – ‘dd-mm-yyyy’ |
| `risk_profile` | [`RiskProfile2`](../../doc/models/risk-profile-2.md) | Required | Defines the user’s risk profile. Note that Risk Profiles are mapped to portfolio access.             For example, a Conservative investor has access to portfolios 1-8 (or 50% Equity) while an Aggressive             investor has access to all 16 portfolios (up to 90% Equity). This is configurable. |
| `compute_social_security` | `bool` | Optional | When set to true computes the social security.                 Mandatory fields (part of memberList) needed for social security are: “DOB”, “currentSalary”, “socialSecurityStartAge”<br><br>**Default**: `False` |
| `use_social_security_for_goals` | `bool` | Optional | When set to “true” uses Social Security to meet the withdrawals.             If set to “false”, and when 'computeSocialSecurity' is set as 'true' - only computes the Social Security but does not use it to fulfil the goals.             In cases social security (post-tax) is greater than the withdrawal amount, the social security is collected into the taxable accounts.             If set to “true”, a taxable account must be present. This is because there can be instances where there are no goals in a given year but an incoming social security infusion.             This infusion can only go into a taxable account.<br><br>**Default**: `False` |
| `cashflow_date` | `str` | Optional | Cashflow date of the goal - this is the date (year is ignored) on which             infusions/withdrawals would be realized for the goal. This parameter is optional.                 If not passed or value is null, the algorithm would consider the first reallocation date as the cashflow date.                     Scheduled cashflows should be planned for a date prior to the 29th of any month. |
| `infusion_type` | [`InfusionType2`](../../doc/models/infusion-type-2.md) | Required | Defines if the infusions are at the yearly level or monthly level. |
| `cola_rate` | `float` | Optional | Defines the Cost-of-Living Adjustment to be used for Social Security amount computations.<br><br>**Default**: `0` |
| `tax_rates` | [`TaxRatesDic2`](../../doc/models/tax-rates-dic-2.md) | Required | Consists of tax rates applicable pre & post-retirement for the entire household |
| `household` | [`HouseholdGoeForTaxesObj2`](../../doc/models/household-goe-for-taxes-obj-2.md) | Required | contains all information about all the participants. |
| `accounts` | [`List[GoeToAccountAttr]`](../../doc/models/goe-to-account-attr.md) | Required | Details of different accounts associated with unique memberID in the household.  <br>                    Note:  <br>                    A single account can be associated with multiple members within the household.                     This would generally be the case with joint taxable accounts. |
| `goal_profile_list` | [`List[GoalProfileGoeForTaxesAttr]`](../../doc/models/goal-profile-goe-for-taxes-attr.md) | Required | Details related to the withdrawals associated with the plan where a plan is defined as a collection of goals. |
| `policy` | [`List[PolicyDetails]`](../../doc/models/policy-details.md) | Optional | Contains details about the policy validation associated with the Platform Partner. In this example,             the array includes participantType and callType, however, the dictionary is open and Platform Partners are able to send other fields to define their respective API Policy. |
| `account_held_away` | `bool` | Optional | To be set to True if the account is a held away account |
| `mean_return` | `float` | Optional | Mean return value for the AHA account. Can be set to null or ignored if ‘accountHeldAway’ is set to False |
| `standard_deviation` | `float` | Optional | Standard deviation for the AHA account. Can be set to null or ignored if ‘accountHeldAway’ is set to False |
| `equity_allocation` | `float` | Optional | The Equity '%' for the AHA account. If this value is provided, the mean and standard deviation is mapped to the GOE managed portfolios. Can be set to null or ignored if ‘accountHeldAway’ is set to False. |
| `lock_expiry_date` | `str` | Optional | The AHA account is considered locked and unavailable for withdrawals till this date. Note that however contributions and RMDs will always be processed. Can be set to null or ignored if ‘accountHeldAway’ is set to False. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.goal_profile_goe_for_taxes_attr import GoalProfileGoeForTaxesAttr
from goeapi.models.goe_for_taxes_input_model import GoeForTaxesInputModel
from goeapi.models.goe_to_account_attr import GoeToAccountAttr
from goeapi.models.goe_to_cashflow_details_2 import GoeToCashflowDetails2
from goeapi.models.goe_to_category import GoeToCategory
from goeapi.models.household_goe_for_taxes_obj_2 import HouseholdGoeForTaxesObj2
from goeapi.models.infusion_type_2 import InfusionType2
from goeapi.models.member_goe_for_taxes_obj import MemberGoeForTaxesObj
from goeapi.models.member_type import MemberType
from goeapi.models.priority_1 import Priority1
from goeapi.models.risk_profile_2 import RiskProfile2
from goeapi.models.tax_rates_dic_2 import TaxRatesDic2

goe_for_taxes_input_model = GoeForTaxesInputModel(
    reallocate=False,
    is_new_risk_profile=False,
    is_new_investment_tenure=False,
    is_new_goal_priority=False,
    is_new_goal=False,
    get_path=True,
    current_portfolio_id=None,
    risk_profile=RiskProfile2.AGGRESSIVE,
    infusion_type=InfusionType2.YEARLY,
    tax_rates=TaxRatesDic2(
        ltcg_pre_retirement=0.15,
        ltcg_post_retirement=0.1,
        etr_pre_retirement=0.15,
        etr_post_retirement=0.2,
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    household=HouseholdGoeForTaxesObj2(
        household_id='1',
        member_list=[
            MemberGoeForTaxesObj(
                member_type=MemberType.PRIMARY,
                member_id='eff63fdb-1ed8-41be-a0f8-7788fdac728c',
                dob='02-1959',
                current_age=66,
                retirement_age=93,
                current_salary=400,
                social_security_start_age=65,
                tda_balance_for_rmd=74.16,
                rmd_utilized=37.72,
                existing_monthly_social_security_amount=10,
                additional_properties={
                    'lifeExpectancy': jsonpickle.decode('93')
                }
            )
        ],
        state_of_residence='KS',
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    accounts=[
        GoeToAccountAttr(
            account_id='dbcd5e3d-55fb-45f6-a654-d720f056a071',
            taxability_type='D',
            member_i_ds=[
                'eff63fdb-1ed8-41be-a0f8-7788fdac728c'
            ],
            current_balance=2,
            current_holdings=[
                GoeToCategory(
                    category_name='CASH',
                    category_id='10',
                    category_price=1,
                    quantity=2,
                    cost_basis=2,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            cashflow_details=GoeToCashflowDetails2(
                start_date='02-05-2025',
                end_date='02-05-2051',
                cashflow_amt=[
                    2500,
                    2575,
                    2652,
                    2732,
                    2814,
                    2898,
                    2985,
                    3075,
                    3167,
                    3262,
                    3360,
                    3461,
                    3564,
                    3671,
                    3781,
                    3895,
                    4012,
                    4132,
                    4256,
                    4384,
                    4515,
                    4651,
                    4790,
                    4934,
                    5082,
                    5234,
                    5391
                ],
                additional_properties={
                    'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                }
            ),
            account_type='IRA',
            additional_properties={
                'accountHeldAway': jsonpickle.decode('false'),
                'lockExpiry': jsonpickle.decode('{"key1":"val1","key2":"val2"}'),
                'meanReturn': jsonpickle.decode('0.03'),
                'standardDeviation': jsonpickle.decode('0.04')
            }
        )
    ],
    goal_profile_list=[
        GoalProfileGoeForTaxesAttr(
            goal_id='39623865346539642d366234362d343639362d393332332d356134356563653030336130',
            start_date='02-05-2052',
            end_date='02-05-2052',
            priority=Priority1.NEED,
            goal_purpose='non-education',
            goal_amt=[
                666
            ],
            scenario_type='retirement',
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    is_near_term_volatility=False,
    curr_date='02-05-2025',
    compute_social_security=False,
    use_social_security_for_goals=True,
    cashflow_date='02-05-2025',
    cola_rate=0.03,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

