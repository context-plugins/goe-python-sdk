
# Wealth Path 2

Priority based path of wealth across the investment tenure         (corresponding to the end of each reallocation date).  If additional wealth paths are         requested, a dictionary of 3 wealth paths and wealth path percentiles is returned – covered in the next 2 rows         The probability levels can be configured.

*This model accepts additional fields of type Any.*

## Structure

`WealthPath2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `default` | `List[float]` | Required | Wealth paths corresponding to the priority-based probability level are returned. |
| `pessimistic` | `List[float]` | Required | Wealth paths corresponding to the Pessimistic probability level are returned |
| `optimistic` | `List[float]` | Required | Wealth paths corresponding to the Optimistic probability level are returned |
| `default_percentile` | `str` | Required | Percentile values corresponding to default path. |
| `pessimistic_percentile` | `str` | Required | Percentile values corresponding to Pessimistic path. |
| `optimistic_percentile` | `str` | Required | Percentile values corresponding to Optimistic path. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.wealth_path_2 import WealthPath2

wealth_path_2 = WealthPath2(
    default=[
        17.58,
        17.59,
        17.6
    ],
    pessimistic=[
        141.04
    ],
    optimistic=[
        134.14
    ],
    default_percentile='defaultPercentile8',
    pessimistic_percentile='pessimisticPercentile6',
    optimistic_percentile='optimisticPercentile4',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

