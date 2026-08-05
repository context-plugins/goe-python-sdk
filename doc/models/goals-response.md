
# Goals Response

*This model accepts additional fields of type Any.*

## Structure

`GoalsResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `goal_id` | `str` | Required | Unique identifier as presented in the request payload. |
| `goal_amt` | `List[float]` | Required | Original withdrawals associated with goals - as defined by a participant. |
| `start_date` | `str` | Required | Start date of a goal – as specified in the request payload. Valid Date Format: DD-MM-YYYY. |
| `end_date` | `str` | Required | End date of a goal – as specified in the request payload. Valid Date Format: DD-MM-YYYY. |
| `modified_goal_amt` | `List[float]` | Required | Withdrawals modified i.e., reduced – based on the modification logic. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.goals_response import GoalsResponse

goals_response = GoalsResponse(
    goal_id='Goal2',
    goal_amt=[
        65.89,
        65.9
    ],
    start_date='01-12-2023',
    end_date='30-11-2025',
    modified_goal_amt=[
        215.52,
        215.53,
        215.54
    ],
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

