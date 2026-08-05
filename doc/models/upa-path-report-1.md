
# Upa Path Report 1

<b>For the Original Plan:</b>            GOE’s outputs including estimated portfolio path, wealth path, etc.

*This model accepts additional fields of type Any.*

## Structure

`UpaPathReport1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `portfolio_path` | `List[int]` | Required | GOE’s expected portfolio path across the investment tenure. |
| `wealth_path` | `List[float]` | Required | Priority based path across the investment tenure. |
| `worst_case_path` | `List[float]` | Required | Represents the pessimistic scenario of a wealth path.                     The default value corresponds to 1% probability (99 percentile). This could be customized using the admin portal. |
| `best_case_path` | `List[float]` | Required | Represents the optimistic scenario of a wealth path. The default value corresponds to 1% probability (99 percentile).                     This could be customized using the admin portal. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.upa_path_report_1 import UpaPathReport1

upa_path_report_1 = UpaPathReport1(
    portfolio_path=[
        135,
        136
    ],
    wealth_path=[
        6.33
    ],
    worst_case_path=[
        249.36,
        249.37,
        249.38
    ],
    best_case_path=[
        171.42,
        171.41
    ],
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

