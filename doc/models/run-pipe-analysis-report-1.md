
# Run Pipe Analysis Report 1

Captures various important recommendations and outputs from the GOE engine.

*This model accepts additional fields of type Any.*

## Structure

`RunPipeAnalysisReport1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `current_goal_probability` | `float` | Required | GOE’s estimated probability to achieve the goal target wealth. This is rounded to 4 decimal places.<br><br>**Constraints**: `>= 0.0001`, `<= 0.99` |
| `recommended_portfolio_id` | `int` | Required | GOE’s current recommended portfolio index. <br>                     Note: Portfolio chosen from the list of all available portfolios to the goal.<br><br>**Constraints**: `>= 1` |
| `meet_goal_priority` | `bool` | Required | Checks if goal probability is more than the target probability corresponding to         the goal priority – Target probabilities for all goal priorities (Need, Want, Wish and Dream) are set in the GOE config.         Note: If ‘true’, goal probability achieves the target probability – goal probability to be shown on the front end.         If ‘false’, goal probability falls short of the target probability –goal probability to be shown along with infusion and tenure recommendations |
| `is_goal_realistic` | `bool` | Required | To understand if the goal can be met with a reasonable probability (set by the ‘unrealistic’ goal probability value in the GOE config).         If current goal probability < desired target goal probability (defined by the goal priority), the goal is termed unrealistic <br>         Note: Flag will be set to False if the current goal probability is less than the probability threshold for realistic goal for all cases irrespective. <br>         If ‘false’, goal is unrealistic - need to alert the user on the front end with a message such as ‘Goal is not realistic, please try reducing your target         goal amount or increasing your initial investment’ |
| `one_time_top_up` | `float` | Required | Suggested one-time top-up amount that aims to improve the goal probability to meet the target goal probability.                     This is rounded to the nearest integer.<br><br>**Constraints**: `>= 0` |
| `yearly_top_up_accumulation` | `float` | Required | Suggested recurring yearly top-up amount that aims to improve the goal probability to meet the target goal probability. This would be returned with a value if the infusionType is annual. This is rounded to the nearest integer. This would be 0 if infusionType is monthly. <br> Note: Zero in cases where meet goal priority = ‘true’; Non-zero otherwise.<br><br>**Constraints**: `>= 0` |
| `monthly_top_up_accumulation` | `float` | Required | Suggested recurring monthly top-up amount during the accumulation period that aims to improve             the goal probability to meet the target goal probability. This would be returned only if the infusionType is monthly.             This is rounded to the nearest integer. <br>             Note: Zero in cases where meet goal priority = ‘true’; Non-zero otherwise.<br><br>**Constraints**: `>= 0` |
| `yearly_top_up_decumulation` | `float` | Required | Suggested recurring yearly decumulation amount that aims to improve the goal probability to meet the target goal probability.             This would be returned only if the infusionType is annual. This is rounded to the nearest integer. |
| `monthly_top_up_decumulation` | `float` | Required | Suggested recurring monthly top-up decumulation amount that aims to improve the goal probability to meet the target         goal probability, this value would be populated only in cases of decumulation of withdrawal scenario. This would be returned only         if the infusionType is monthly. This is rounded to the nearest integer. |
| `recommended_tenure` | `str` | Required | For scenarios with goal probability less than 50%: <br>                     • If original tenure between 1 - 8 years –extended/reduced tenure 2 years to 4 years <br>                     • If original tenure between 9 – 14 years – extended/reduced tenure 4 years to 8 years <br>                     • If original tenure greater than equal to 15 years –extended/reduced tenure 5 years to 10 years <br>         For scenarios with goal probability greater than or equal to 50%, extended/reduced tenure = 2 years to 4 years for all cases.         The algorithm recommends standard tenure increments/decrements based on the tenure input and the goal probability (calculated using current and end date).         Cases where tenure recommendation isn’t valid/required will show the recommendation as NA.         For retirement cases, where there is accumulation followed by decumulation, the extension is based on years to retirement and not on original tenure |
| `bankruptcy_msg` | `str` | Required | Message flagging an expected bankruptcy (goal running out of money) in any year.         The algorithm recommends standard tenure increments/decrements based on the tenure input and the goal probability (calculated using current and end date). <br>        Note: If ‘NA’, bankruptcy is unlikely to happen during the goal tenure.In bankruptcy cases, response would be similar to         ‘Bankruptcy is likely to happen in year 1’. |
| `message` | `str` | Required | Captures any message from the API after it is done processing the request. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.run_pipe_analysis_report_1 import RunPipeAnalysisReport1

run_pipe_analysis_report_1 = RunPipeAnalysisReport1(
    current_goal_probability=0.99,
    recommended_portfolio_id=212,
    meet_goal_priority=False,
    is_goal_realistic=False,
    one_time_top_up=127.24,
    yearly_top_up_accumulation=100.96,
    monthly_top_up_accumulation=56.24,
    yearly_top_up_decumulation=138.12,
    monthly_top_up_decumulation=33.06,
    recommended_tenure='recommendedTenure6',
    bankruptcy_msg='bankruptcyMsg4',
    message='message8',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

