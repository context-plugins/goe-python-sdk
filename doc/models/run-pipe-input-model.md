
# Run Pipe Input Model

*This model accepts additional fields of type Any.*

## Structure

`RunPipeInputModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `is_new_goal_priority` | `bool` | Required | If investor/end user changes the goal priority in between the re-allocation dates,             this is set to ‘true’. For first time calls to GOE, this needs to be set to ‘true’. |
| `is_new_investment_tenure` | `bool` | Required | If investor/end user changes the goal investment tenure after onboarding and before the next immediate re-allocation date,             this is set to ‘true’. For first time calls to GOE, this needs to be set to ‘true’. |
| `is_new_risk_profile` | `bool` | Required | If the risk profile of the investor has changed, this should be set to ‘true’.                     For first time calls to GOE, this needs to be set to ‘true’. |
| `is_new_goal` | `bool` | Required | If investor/end user changes the goal amount, in between the re-allocation dates, this is set to ‘true’.                     For retirement scenarios, this would be a change in retirement income goal, while for a capital accumulation goal,                     this would be a change in the lumpsum accumulation target. For first time calls to GOE, this needs to be set to ‘true’. |
| `reallocate` | `bool` | Optional | If the client wants GOE to reallocate between the scheduled re-allocation dates, this should be set to ‘true’.<br><br>**Default**: `False` |
| `cashflow_date` | `str` | Optional | Cashflow date of the goal - this is the date (year is ignored) on which infusions/withdrawals                                                                 would be realized for the goal. Format is "dd-mm-yyyy"                                                                 If not passed or value is null, the algorithm would consider the first reallocation date as the cashflow date. |
| `get_path` | `bool` | Required | Show ideal portfolio path over time. If getPath parameter is set to False, the portfolio path would not be returned in the response payload |
| `reallocation_freq` | [`ReallocationFreq`](../../doc/models/reallocation-freq.md) | Required | Describes the frequency of re-allocation. |
| `goal_amount` | `float` | Required | Defines the target wealth value associated with the goal at end of goal tenure.<br><br>**Constraints**: `>= 0` |
| `initial_investment` | `float` | Required | Defines the initial investment amount to the goal.<br><br>**Constraints**: `>= 0` |
| `current_wealth` | `float` | Required | Current wealth when the GOE is being called or executed. At the time of initial onboarding, currentWealth = initialInvestment.                                                             At subsequent re-allocation dates, currentWealth would be the portfolio account value at the time. |
| `start_date` | `str` | Required | Defines the start date of goal.Valid input format is date – ‘dd-mm-yyyy’ |
| `goal_start_date` | `str` | Optional | Defines the goal's start date. Must be greater than or equal to startDate field and in DD-MM-YYYY format. Default value is Null.             Mandatory If useCapsAndFloors is True and currentAge is not present |
| `end_date` | `str` | Required | Defines the end date of goal.Valid input format is date – ‘dd-mm-yyyy’ |
| `curr_date` | `str` | Optional | This is an optional parameter that can be used to simulate the current date to be the specified value.                     GOE will process the request as if you are making the API call on the specified date.                     If not passed, the current system date will be used as the current date.                     Valid input format is date – ‘dd-mm-yyyy’. |
| `goal_priority` | [`GoalPriority1`](../../doc/models/goal-priority-1.md) | Required | Defines the importance a goal holds for a specific user. Order of priority is Need > Want > Wish > Dream          goalPriority can be from 1 to 4 levels. However, note that Goal priority defines the target probabilities and the loss threshold values. |
| `current_portfolio_id` | `int` | Required | Displays the current portfolio index that the goal is allocated to;                     if GOE is getting executed for the first time, it should be null. |
| `infusions` | `List[float]` | Required | Cash flows from the user, recurring payments yearly <br>                                                        The length for this parameter is dynamic depending on the goal tenure, start date and end date.<br>                                                        The reference will always be on the created date. So, the first infusion will be on the first day of the goal <br>                                                        followed by infusions every year/month followed by the last infusion/withdrawal on the last day of the goal.<br>                                                         The values are positive in case of infusions; negative in case of withdrawals; zero in case of no cashflows; frequency depends on ‘infusion_type’ parameter |
| `risk_profile` | [`RiskProfile5`](../../doc/models/risk-profile-5.md) | Required | Defines the user’s risk profile – does not vary by goal for each investor.             On a default basis, GOE is configured for three Risk Profile levels, but it can be customized for up to five levels.             Note that Risk Profiles are mapped to portfolio access.This is nullable and non mandatory if useCapsAndFloors is true |
| `scenario_type` | [`ScenarioType4`](../../doc/models/scenario-type-4.md) | Required | Determines the type of the scenario, the suggested portfolio and the wealth glide path is created accordingly.                     ‘regular’ for regular goals accumulation goals where cash flows are positive (contributions) and with a typical target wealth                     ‘retirement’ for scenarios where a decumulation period is included: <br>                     1. Scenarios with an accumulation period (and an initial wealth) & positive cash flows followed                     by a decumulation period with withdrawals (negative cash flows) with or without an inheritance <br>                     2. Scenarios with an initial wealth followed by a decumulation period with or without an inheritance. |
| `infusion_type` | [`InfusionType1`](../../doc/models/infusion-type-1.md) | Required | Indicates the frequency of cash flows – determines the cash flow array corresponding to the ‘infusions’ parameter. |
| `current_age` | `int` | Optional | Captures the current age of the investor.             Optional Parameter. Need to be passed if useCapsAndFloors is set to True or ‘requiredDataAvailable’ is set to False. |
| `retirement_age` | `int` | Optional | Captures the retirement age of the investor.                 Optional Parameter.Considered as 65 if not passed |
| `risk_override` | bool \| None | Optional | This is a container for any-of cases. |
| `engaged_participant` | bool \| None | Optional | This is a container for any-of cases. |
| `required_data_available` | `bool` | Optional | This indicates to GOE if all the mandatory data parameters that are required to run the GOE algorithm are available or not.          If all the mandatory fields are available, this parameter is set to true, and they need be passed to run GOE.         If all the mandatory fields are not available, this parameter is set to false, and they need not be passed to run GOE except the 'currentAge' and         the “retirementAge”; The API response body would contain only the recommended portfolio and the portfolio path, which is derived from a pre-determined glide path         based on the current age and the retirement age (this would be defaulted to 65 if not passed). All other response parameters would be null.<br><br>**Default**: `True` |
| `wealth_path_probabilities` | List[float] \| None | Optional | This is a container for any-of cases. |
| `plan_id` | `str` | Optional | Plan ID of the participant. |
| `participant_id` | `str` | Optional | ID of the participant. |
| `source_id` | `str` | Optional | Source ID of the plan |
| `use_caps_and_floors` | `bool` | Optional | This is an optional parameter set as false by default. If this is passed as ‘true’ – the minimum and maximum equity allocation at any             given year would be restricted based on the number of years to goal;Either goalStartDate                 or the ‘currentAge’ is required if this is set to True. If set to true 'Risk Profile' is ignored.<br><br>**Default**: `False` |
| `target_portfolio` | `int` | Optional | Defines the portfolio ID that has to be held across the entire goal horizon             during single portfolio mode i.e. buy and hold strategy. <br>             Mandatory if mode is 'single-portfolio'​ |
| `mode` | `str` | Optional | Determines the custom modes that can be invoked by GOE API |
| `policy` | [`List[PolicyDetails]`](../../doc/models/policy-details.md) | Optional | Contains details about the policy validation associated with the Platform Partner. In this example,             the array includes participantType and callType, however, the dictionary is open and Platform Partners are able to send other fields to define their respective API Policy. |
| `cashflow` | [`List[CashFlowDict2]`](../../doc/models/cash-flow-dict-2.md) | Optional | Cannot be a empty list. If defined, should have objects with below attributes. Multiple objects of each type should not be allowed. For example, you cannot allow two objects of type "GOAL". When "cashflow" is passed, "infusions" and "goalAmount" will be optional. Otherwise these two will be mandatory. The field is optional if "infusions" is provided, otherwise mandatory. |
| `transition_matrix_id` | `str` | Optional | transitionMatrixID defines the ID of the transaction fee matrix that needs to be used for calculating transaction fee in the algo if transaction fee is set to true on admin portal.             When transaction fees = true on admin portal: Yes (Mandatory)             When transaction fees = false on admin portal: No (Optional, defaults to None)                 String key following a startYear_EndYear naming convention (e.g., '2025_2026' for inter-year, '2025_2025' or '2026_2026' for intra-year). |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.goal_priority_1 import GoalPriority1
from goeapi.models.infusion_type_1 import InfusionType1
from goeapi.models.reallocation_freq import ReallocationFreq
from goeapi.models.risk_profile_5 import RiskProfile5
from goeapi.models.run_pipe_input_model import RunPipeInputModel
from goeapi.models.scenario_type_4 import ScenarioType4

run_pipe_input_model = RunPipeInputModel(
    is_new_goal_priority=True,
    is_new_investment_tenure=True,
    is_new_risk_profile=True,
    is_new_goal=True,
    get_path=True,
    reallocation_freq=ReallocationFreq.YEARLY,
    goal_amount=1000000,
    initial_investment=250000,
    current_wealth=250000,
    start_date='13-01-2025',
    end_date='10-10-2059',
    goal_priority=GoalPriority1.NEED,
    current_portfolio_id=None,
    infusions=[
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
    risk_profile=RiskProfile5.AGGRESSIVE,
    scenario_type=ScenarioType4.REGULAR,
    infusion_type=InfusionType1.YEARLY,
    reallocate=True,
    cashflow_date='11-10-2025',
    goal_start_date='goalStartDate0',
    curr_date='13-01-2025',
    current_age=39,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

