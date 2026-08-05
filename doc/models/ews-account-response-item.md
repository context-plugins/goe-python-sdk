
# Ews Account Response Item

*This model accepts additional fields of type Any.*

## Structure

`EwsAccountResponseItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `investment_id` | `str` | Required | Account identifier |
| `goal_split_infusion` | [`List[EwsGoalSplitInfusionItem]`](../../doc/models/ews-goal-split-infusion-item.md) | Required | Goal-wise infusion breakdown for this account |
| `goal_split_lumpsum` | [`List[EwsGoalSplitLumpsumItem]`](../../doc/models/ews-goal-split-lumpsum-item.md) | Required | One-time lumpsum allocations from this account |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.ews_account_response_item import EwsAccountResponseItem
from goeapi.models.ews_goal_split_infusion_item import EwsGoalSplitInfusionItem
from goeapi.models.ews_goal_split_lumpsum_item import EwsGoalSplitLumpsumItem
from goeapi.models.ews_series_value import EwsSeriesValue

ews_account_response_item = EwsAccountResponseItem(
    investment_id='investmentId2',
    goal_split_infusion=[
        EwsGoalSplitInfusionItem(
            goal_id='goalId8',
            cashflow=[
                EwsSeriesValue(
                    value=150.28,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            first_contribution_date='firstContributionDate0',
            first_contribution_amount=44,
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    goal_split_lumpsum=[
        EwsGoalSplitLumpsumItem(
            goal_id='goalId0',
            value=109.98,
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

