
# Ews Goal Split Lumpsum Item

*This model accepts additional fields of type Any.*

## Structure

`EwsGoalSplitLumpsumItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `goal_id` | `str` | Required | Goal receiving lumpsum |
| `value` | `float` | Required | Lumpsum amount<br><br>**Constraints**: `>= 0` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.ews_goal_split_lumpsum_item import EwsGoalSplitLumpsumItem

ews_goal_split_lumpsum_item = EwsGoalSplitLumpsumItem(
    goal_id='goalId8',
    value=85.7,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

