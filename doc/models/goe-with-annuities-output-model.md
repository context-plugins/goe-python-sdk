
# Goe with Annuities Output Model

*This model accepts additional fields of type Any.*

## Structure

`GoeWithAnnuitiesOutputModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `retirement_goal` | `float` | Required | Recommended yearly retirement income goal |
| `retirement_goal_min` | `float` | Required | Minimum recommended yearly retirement income goal |
| `retirement_goal_max` | `float` | Required | Maximum recommended yearly retirement income goal |
| `income_from_outside_assets` | `float` | Required | Projected income from outside assets. |
| `income_from_ss` | `float` | Required | Projected Social Security income |
| `income_from_others` | `float` | Required | Projected income from other sources. |
| `allocation_to_annuities` | `float` | Required | Balance to be allocated to annuities. |
| `allocation_to_goe` | `float` | Required | Balance to be allocated to GOE. |
| `recommended_portfolio_id` | `int` | Required | Recommended portfolio index for the participant. |
| `retirement_goal_probability` | `float` | Required | Probability of achieving the retirement goal |
| `recommended_consumption` | `float` | Required | Recommended yearly consumption |
| `rmd` | `float` | Required | Recommended RMD distribution. Null before RMD start age and valid value above RMD start age. |
| `income_from_guaranteed` | `float` | Required | Income from other non-guaranteed sources. |
| `monthly_topup_accumulation` | `float` | Required | Save more recommendation. |
| `monthly_topup_decumulation` | `float` | Required | Spend less recommendation. |
| `yearly_topup_accumulation` | `float` | Required | Save more recommendation. |
| `yearly_topup_decumulation` | `float` | Required | Spend less recommendation. |
| `recommended_tenure` | `str` | Required | Retire later recommendation. |
| `income_from_goe` | `float` | Required | Projected income from GOE account. |
| `income_from_annuities` | `float` | Required | Projected income from annuities. |
| `portfolio_path` | `List[int]` | Required | GOE’s expected portfolio path across the goal tenure.(corresponding to the date). <br>            Note: Represents the portfolios to be allocated into at the beginning of each re-allocation date. Asset class allocations corresponding to the portfolio indexes to be shown on the front end. |
| `wealth_path` | List[float] \| Dict[str, Any] | Required | This is a container for any-of cases. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.goe_with_annuities_output_model import GoeWithAnnuitiesOutputModel

goe_with_annuities_output_model = GoeWithAnnuitiesOutputModel(
    retirement_goal=60000,
    retirement_goal_min=50000,
    retirement_goal_max=75000,
    income_from_outside_assets=2000,
    income_from_ss=2000,
    income_from_others=10000,
    allocation_to_annuities=1000,
    allocation_to_goe=20000,
    recommended_portfolio_id=8,
    retirement_goal_probability=0.8513,
    recommended_consumption=60000,
    rmd=10000,
    income_from_guaranteed=2000,
    monthly_topup_accumulation=500,
    monthly_topup_decumulation=300,
    yearly_topup_accumulation=6000,
    yearly_topup_decumulation=3600,
    recommended_tenure='67',
    income_from_goe=10000,
    income_from_annuities=15000,
    portfolio_path=[
        5,
        5,
        5,
        3,
        1
    ],
    wealth_path=[
        921537,
        942172.9,
        963270.91
    ],
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

