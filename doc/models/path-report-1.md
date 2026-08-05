
# Path Report 1

Captures lookforward portfolio and wealth paths as calcualted by the GOE engine.

*This model accepts additional fields of type Any.*

## Structure

`PathReport1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `portfolio_path` | `List[int]` | Required | GOE’s expected portfolio path across the goal tenure (corresponding to the beginning of each reallocation date). <br>         Note: Represents the portfolios to be allocated into at the beginning of each re-allocation date.Asset class allocations         corresponding to the portfolio indexes to be shown on the front end |
| `wealth_path` | [`WealthPath2`](../../doc/models/wealth-path-2.md) | Required | Priority based path of wealth across the investment tenure         (corresponding to the end of each reallocation date).  If additional wealth paths are         requested, a dictionary of 3 wealth paths and wealth path percentiles is returned – covered in the next 2 rows         The probability levels can be configured. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.path_report_1 import PathReport1
from goeapi.models.wealth_path_2 import WealthPath2

path_report_1 = PathReport1(
    portfolio_path=[
        29
    ],
    wealth_path=WealthPath2(
        default=[
            94.4
        ],
        pessimistic=[
            35.74,
            35.75,
            35.76
        ],
        optimistic=[
            210.96,
            210.97
        ],
        default_percentile='defaultPercentile6',
        pessimistic_percentile='pessimisticPercentile4',
        optimistic_percentile='optimisticPercentile6',
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

