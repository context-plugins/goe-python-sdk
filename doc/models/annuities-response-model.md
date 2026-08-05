
# Annuities Response Model

*This model accepts additional fields of type Any.*

## Structure

`AnnuitiesResponseModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status_code` | `int` | Required | - |
| `message` | `str` | Required | - |
| `advice_id` | `str` | Required | Unique identifier for each response. The ID can be used as an input in the /api/goe-api/advice-status API request. |
| `body` | [`GoeWithAnnuitiesOutputModel`](../../doc/models/goe-with-annuities-output-model.md) | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.annuities_response_model import AnnuitiesResponseModel
from goeapi.models.goe_with_annuities_output_model import GoeWithAnnuitiesOutputModel

annuities_response_model = AnnuitiesResponseModel(
    status_code=200,
    message='Success',
    advice_id='adviceID4',
    body=GoeWithAnnuitiesOutputModel(
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
    ),
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

