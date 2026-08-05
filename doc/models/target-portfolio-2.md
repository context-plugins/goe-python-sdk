
# Target Portfolio 2

Target portfolio defines the risk profile for AUA accounts in case user wants to use custom portfolio mode.

*This model accepts additional fields of type Any.*

## Structure

`TargetPortfolio2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mean_return` | `float` | Optional | Mean return value for the AUA account, in case user wants to use custom portfolio mode. |
| `standard_deviation` | `float` | Optional | Standard deviation for the AUA account, in case user wants to use custom portfolio mode. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.target_portfolio_2 import TargetPortfolio2

target_portfolio_2 = TargetPortfolio2(
    mean_return=0.05,
    standard_deviation=0.01,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

