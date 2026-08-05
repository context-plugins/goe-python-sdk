
# Ews Goal Split Infusion Item

*This model accepts additional fields of type Any.*

## Structure

`EwsGoalSplitInfusionItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `goal_id` | `str` | Required | Goal receiving infusions |
| `cashflow` | [`List[EwsSeriesValue]`](../../doc/models/ews-series-value.md) | Required | Timeline of infusions to this goal |
| `first_contribution_date` | `str` | Required | Date of first contribution |
| `first_contribution_amount` | `int` | Required | Value at the date of first contribution |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.ews_goal_split_infusion_item import EwsGoalSplitInfusionItem
from goeapi.models.ews_series_value import EwsSeriesValue

ews_goal_split_infusion_item = EwsGoalSplitInfusionItem(
    goal_id='goalId4',
    cashflow=[
        EwsSeriesValue(
            value=150.28,
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    first_contribution_date='firstContributionDate6',
    first_contribution_amount=90,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

