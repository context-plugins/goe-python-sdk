
# Unified Portfolio Advice Input Model V4

*This model accepts additional fields of type Any.*

## Structure

`UnifiedPortfolioAdviceInputModelV4`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `is_new_goal_priority` | `bool` | Required | If the investor/end user changes the priority of any of the goals within the plan,             in between the re-allocation dates, this should be set to ‘true’.             For new plans, this needs to be ‘true’. |
| `is_new_risk_profile` | `bool` | Required | If the risk profile of the investor/end user  has changed, this should be set to ‘true’.                      For new plans, this needs to be set to ‘true’. |
| `is_new_investment_tenure` | `bool` | Required | If the investor/end user changes the goal investment tenure of any of the goals within the plan,                      in between re-allocation dates, this should be set to ‘true’.For new plans, this needs to be ‘true’. |
| `is_new_goal` | `bool` | Required | If the investor/end user changes the goal amount in between the re-allocation dates,              this is set to ‘true’. For retirement scenarios, this would be a change in the retirement income goal,                  while for a capital accumulation goal, this would be a change in the lump sum accumulation target.                      For new plans, this needs to be set to ‘true’. |
| `cashflow_date` | `str` | Optional | Cashflow date of the plan - this is typically the date (year is ignored) on which infusions/withdrawals would happen for the goals.                                                                 Format is "dd-mm-yyyy".                                                                 If the cashflowDate parameter is set to null, the algorithm would consider the first reallocation date as the cashflow date. |
| `get_path` | `bool` | Required | Show portfolio path, wealth path and wealth node path over time. If getPath parameter is set to true, the paths would be returned in the response payload. |
| `reallocation_freq` | [`ReallocationFreq2`](../../doc/models/reallocation-freq-2.md) | Required | Describes the frequency of re-allocation. If set to 'yearly',             GOE would assume the re-allocation to happen once a year.                Response parameters such as portfolio path and wealth path would have one value each year. |
| `initial_investment` | `float` | Required | Defines the lump sum initial welath of the plan.<br><br>**Constraints**: `>= 0` |
| `current_wealth` | `float` | Required | Current wealth of the plan/combined goal when the GOE is being called or executed At the time of initial onboarding, currentWealth is null. On subsequent dates, currentWealth would be the portfolio account value at the time. |
| `current_portfolio_id` | `int` | Required | Current portfolio index that the combined plan is allocated to; if algo is getting executed for the first time (onboarding call), it should be null.        For cases where updated probability is needed in between the scheduled re-allocation dates, this parameter should be set to the portfolio index the investor is assigned to. |
| `infusions` | `List[float]` | Required | Net cash flow array for the plan/combined goal. Positive in the case of infusions; negative in             case of withdrawals; zero in case of no cashflows; frequency depends on ‘infusionType’.            For subsequent calls, the infusions array needs to be adjusted based on the time that has elapsed. |
| `risk_profile` | [`RiskProfile6`](../../doc/models/risk-profile-6.md) | Required | Defines the user’s risk profile. Note that Risk Profiles are mapped to portfolio access. For example, a Conservative investor has access to portfolios 1-8 (or 50% Equity) while an Aggressive investor has access to all 16 portfolios (up to 90% Equity).             On a default basis, GOE is configured for three Risk Profile levels, but it can be customized for up to five levels. |
| `infusion_type` | [`Infusiontype5`](../../doc/models/infusiontype-5.md) | Required | Indicates the frequency of cash flows – Determines the cash flow array corresponding to the ‘infusions’ parameter. |
| `curr_date` | `str` | Optional | This is an optional parameter that can be used to simulate the current date being the specified value. <br>                                                     GOE will process the request as if you are making the API call on the specified date. If not passed, the current system date will be used as the current date.<br><br>**Default**: `"System Date"` |
| `goal_profile_list` | [`List[GoalProfile]`](../../doc/models/goal-profile.md) | Required | A list containing parameters for different goals. Each goal in the list would have a goal ID,              goal amount, start date, end date, and priority.For subsequent calls,                 the goalProfileList needs to be updated based on the time that has elapsed. If a goal has expired, then it needs to be removed from the goalProfileList. |
| `plan_id` | `str` | Optional | Plan ID of the participant. |
| `participant_id` | `str` | Optional | ID of the participant. |
| `source_id` | `str` | Optional | Source ID of the plan |
| `reallocate` | `bool` | Optional | If the client wants GOE to reallocate between the scheduled re-allocation dates, this should be set to ‘true’.<br><br>**Default**: `False` |
| `calibrate_goal_rec` | `bool` | Optional | If the client wants GOE to reallocate between the scheduled re-allocation dates, this should be set to ‘true’.            Setting this parameter to true will ensure that GOE runs a calibration logic for the recommendations so                 that incorporating the recommendations would result in reaching the goal probability target (for example, 85% for a Need priority).<br><br>**Default**: `False` |
| `assets_held_away` | [`List[FixedAsset]`](../../doc/models/fixed-asset.md) | Optional | Array of AHA objects- Only available through certain modes on Admin Portal. |
| `wealth_path_probabilities` | `List[float]` | Optional | This is an optional input parameter. If this input is passed, instead of one wealth path, <br>         the GOE output will have 3 wealth paths –one path at the goal priority probability level and <br>             one path for each of the 2 probability values passed in this input array. |
| `fixed_assets` | [`List[AssetsHeldAwayInfo]`](../../doc/models/assets-held-away-info.md) | Optional | Array of fixed asset objects- Only available through certain modes on Admin Portal. |
| `policy` | [`List[PolicyDetails]`](../../doc/models/policy-details.md) | Optional | Contains details about the policy validation associated with the Platform Partner. In this example,             the array includes participantType and callType, however, the dictionary is open and Platform Partners are able to send other fields to define their respective API Policy. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.goal_profile import GoalProfile
from goeapi.models.infusiontype_5 import Infusiontype5
from goeapi.models.priority import Priority
from goeapi.models.reallocation_freq_2 import ReallocationFreq2
from goeapi.models.risk_profile_6 import RiskProfile6
from goeapi.models.scenariotype_2 import Scenariotype2
from goeapi.models.unified_portfolio_advice_input_model_v_4 import UnifiedPortfolioAdviceInputModelV4

unified_portfolio_advice_input_model_v_4 = UnifiedPortfolioAdviceInputModelV4(
    is_new_goal_priority=True,
    is_new_risk_profile=True,
    is_new_investment_tenure=True,
    is_new_goal=True,
    get_path=True,
    reallocation_freq=ReallocationFreq2.YEARLY,
    initial_investment=86000,
    current_wealth=None,
    current_portfolio_id=None,
    infusions=[
        0,
        4000,
        4000,
        4000,
        4000,
        4000,
        4000,
        4000,
        4000,
        4000,
        -21000,
        -19000,
        -75000,
        -23000,
        -23000,
        -23000
    ],
    risk_profile=RiskProfile6.AGGRESSIVE,
    infusion_type=Infusiontype5.YEARLY,
    goal_profile_list=[
        GoalProfile(
            goal_id='Goal1',
            goal_amt=[
                25000
            ],
            start_date='01-01-2021',
            end_date='01-01-2031',
            priority=Priority.NEED,
            scenario_type=Scenariotype2.REGULAR,
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        GoalProfile(
            goal_id='Goal2',
            goal_amt=[
                52000
            ],
            start_date='01-01-2021',
            end_date='01-01-2033',
            priority=Priority.NEED,
            scenario_type=Scenariotype2.REGULAR,
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        GoalProfile(
            goal_id='Goal3',
            goal_amt=[
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000,
                2000
            ],
            start_date='01-01-2022',
            end_date='01-01-2036',
            priority=Priority.NEED,
            scenario_type=Scenariotype2.RETIREMENT,
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        GoalProfile(
            goal_id='Goal4',
            goal_amt=[
                21000,
                21000,
                21000,
                21000,
                21000
            ],
            start_date='01-01-2032',
            end_date='01-01-2036',
            priority=Priority.NEED,
            scenario_type=Scenariotype2.RETIREMENT,
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    cashflow_date='01-01-2021',
    curr_date='04-01-2021',
    plan_id='planID4',
    participant_id='participantID8',
    source_id='sourceID6',
    calibrate_goal_rec=True,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

