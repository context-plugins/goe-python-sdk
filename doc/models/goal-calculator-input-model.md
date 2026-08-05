
# Goal Calculator Input Model

*This model accepts additional fields of type Any.*

## Structure

`GoalCalculatorInputModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `is_new_goal` | `bool` | Required | If investor/end user changes the goal amount, in between the re-allocation dates, this is set to ‘true’. For retirement scenarios, this would be a change in retirement income goal, while for a capital accumulation goal,                                                 this would be a change in the lumpsum accumulation target. For first time calls to GOE, this needs to be set to ‘true’. |
| `is_new_risk_profile` | `bool` | Required | If investor/end user changes the goal priority in between the re-allocation dates, this is set to ‘true’.                                                 For first time calls to GOE, this needs to be set to ‘true’. |
| `is_new_investment_tenure` | `bool` | Required | If investor/end user changes the goal investment tenure after onboarding and before the next immediate re-allocation date,                                     this is set to ‘true’. For first time calls to GOE, this needs to be set to ‘true’. |
| `is_new_goal_priority` | `bool` | Required | If investor/end user changes the goal priority in between the re-allocation dates, this is set to ‘true’.                                     For new plans, this needs to be ‘true’. |
| `reallocate` | `bool` | Optional | If the client wants GOE to reallocate between the scheduled re-allocation dates, this should be set to ‘true’.<br><br>**Default**: `False` |
| `use_caps_and_floors` | `bool` | Optional | This is an optional parameter set as false by default. If this is passed as ‘true’ – the minimum and maximum             equity allocation at any given year would be restricted based on the number of years to goal;Either goalStartDate or the ‘currentAge’                 is required if this is set to True. If set to true 'Risk Profile' is ignored.<br><br>**Default**: `False` |
| `reallocation_freq` | [`ReallocationFreq`](../../doc/models/reallocation-freq.md) | Required | Describes the frequency of re-allocation. |
| `get_path` | `bool` | Required | Show ideal portfolio path over time. If getPath parameter is set to False, the portfolio path would not be returned in the response payload |
| `current_portfolio_id` | `int` | Required | Displays the current portfolio index that the goal is allocated to;                                                      if GOE is getting executed for the first time, it should be null. |
| `scenario_type` | [`ScenarioType1`](../../doc/models/scenario-type-1.md) | Required | Determines the type of the scenario, the suggested portfolio and the wealth glide path is created accordingly. ‘regular’ for regular goals accumulation goals where cash flows are positive (contributions) and with a typical target wealth ‘retirement’ for scenarios where a decumulation period is included: <br>            1. Scenarios with an accumulation period (and an initial wealth) & positive cash flows followed by a decumulation period with withdrawals (negative cash flows) with or without an inheritance <br>                2. Scenarios with an initial wealth followed by a decumulation period with or without an inheritance. |
| `curr_date` | `str` | Optional | This is an optional parameter that can be used to simulate the current date to be the specified value.                                                     GOE will process the request as if you are making the API call on the specified date. If not passed, the current system date will be used as the current date. |
| `risk_profile` | [`RiskProfile1`](../../doc/models/risk-profile-1.md) | Required | Defines the user’s risk profile – does not vary by goal for each investor. On a default basis, GOE is configured for three Risk Profile levels, but it can be customized for up to five levels. Note that Risk Profiles are mapped to portfolio access.This is nullable and non mandatory if useCapsAndFloors is true. |
| `initial_investment` | `float` | Required | Defines the initial investment amount to the goal.<br><br>**Constraints**: `>= 0` |
| `current_wealth` | `float` | Required | Current wealth when the GOE is being called or executed. At the time of initial onboarding, currentWealth = initialInvestment.                                                             At subsequent re-allocation dates, currentWealth would be the portfolio account value at the time. |
| `cashflow_date` | `str` | Optional | Cashflow date of the goal - this is the date (year is ignored) on which infusions/withdrawals                                                                 would be realized for the goal. Format is "dd-mm-yyyy"                                                                 If not passed or value is null, the algorithm would consider the first reallocation date as the cashflow date. |
| `goal_priority` | [`GoalCalculatorGoalPriorityAttribute`](../../doc/models/goal-calculator-goal-priority-attribute.md) | Required | Defines the importance a goal holds for a specific user. Order of priority is Need > Want > Wish > Dream          goalPriority can be from 1 to 4 levels. However, note that Goal priority defines the target probabilities and the loss threshold values. |
| `goal_amount` | `float` | Required | For regular scenarios, either the goal amount field shouldn't be provided in the input payload, or if provided, it should either be 'null' or '0.         For retirement cases where  the intent is to calculate an appropriate bequest amount, the bequest (“goal_amt”) should be specified as ‘null’ or ‘0’. For other cases, it can any number greater than zero.<br><br>**Constraints**: `>= 0` |
| `start_date` | `str` | Required | Defines the start date of goal. Valid input format is date – ‘dd-mm-yyyy’ |
| `goal_start_date` | `str` | Optional | Defines the goal's start date. Must be greater than the startDate field and in DD-MM-YYYY format. Default value is Null.            Mandatory If useCapsAndFloors is True and currentAge is not present. |
| `end_date` | `str` | Required | Defines the end date of goal. Valid input format is date – ‘dd-mm-yyyy’ |
| `infusion_type` | [`InfusionType1`](../../doc/models/infusion-type-1.md) | Required | Indicates the frequency of cash flows – determines the cash flow array corresponding to the ‘infusions’ parameter. |
| `infusions` | `List[float]` | Required | Cash flows from the user, recurring payments yearly                                                         The length for this parameter is dynamic depending on the goal tenure, start date and end date.                                                        The reference will always be on the created date. So, the first infusion will be on the first day of the goal                                                         followed by infusions every year/month followed by the last infusion/withdrawal on the last day of the goal.                                                         The values are positive in case of infusions; negative in case of withdrawals; zero in case of no cashflows; frequency depends on ‘infusion_type’ parameter.                                                              If each of the withdrawal amounts are set as ‘-1’ in the infusions array, then it is assumed that the income goal needs to be calculated. |
| `current_age` | `int` | Optional | Captures the current age of the investor.<br>         Optional Parameter. Need to be passed if useCapsAndFloors is set to True or ‘requiredDataAvailable’ is set to False. |
| `retirement_age` | `int` | Optional | Captures the retirement age of the investor.             Optional Parameter. Considered as 65 if not passed |
| `policy` | [`List[PolicyDetails]`](../../doc/models/policy-details.md) | Optional | Contains details about the policy validation associated with the Platform Partner. In this example,             the array includes participantType and callType, however, the dictionary is open and Platform Partners are able to send other fields to define their respective API Policy. |
| `engaged_participant` | bool \| None | Optional | This is a container for any-of cases. |
| `last_reallocation_date` | `str` | Optional | The date on which last reallocation call was made to GOE. Format - dd-mm-yyyy |
| `plan_id` | `str` | Optional | Plan ID of the participant. |
| `participant_id` | `str` | Optional | ID of the participant. |
| `source_id` | `str` | Optional | Source ID of the plan |
| `cashflow` | [`List[CashFlowDict1]`](../../doc/models/cash-flow-dict-1.md) | Optional | Cannot be a empty list. If defined, should have objects with below attributes.<br>Multiple objects of each type should not be allowed. For example, you cannot allow two objects of type "GOAL".<br>When "cashflow" is passed, "infusions" and "goalAmount" will be optional. Otherwise these two will be mandatory.<br>The field is optional if "infusions" is provided, otherwise mandatory. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.goal_calculator_goal_priority_attribute import GoalCalculatorGoalPriorityAttribute
from goeapi.models.goal_calculator_input_model import GoalCalculatorInputModel
from goeapi.models.infusion_type_1 import InfusionType1
from goeapi.models.reallocation_freq import ReallocationFreq
from goeapi.models.risk_profile_1 import RiskProfile1
from goeapi.models.scenario_type_1 import ScenarioType1

goal_calculator_input_model = GoalCalculatorInputModel(
    is_new_goal=True,
    is_new_risk_profile=True,
    is_new_investment_tenure=True,
    is_new_goal_priority=True,
    reallocation_freq=ReallocationFreq.YEARLY,
    get_path=False,
    current_portfolio_id=None,
    scenario_type=ScenarioType1.RETIREMENT,
    risk_profile=RiskProfile1.CONSERVATIVE,
    initial_investment=941897,
    current_wealth=941897,
    goal_priority=GoalCalculatorGoalPriorityAttribute.NEED,
    goal_amount=0,
    start_date='01-01-2020',
    end_date='10-10-2023',
    infusion_type=InfusionType1.YEARLY,
    infusions=[
        0,
        4000,
        4000,
        -1,
        0
    ],
    reallocate=True,
    use_caps_and_floors=False,
    curr_date='13-01-2021',
    cashflow_date='25-01-2020',
    goal_start_date='goalStartDate4',
    current_age=15,
    retirement_age=60,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

