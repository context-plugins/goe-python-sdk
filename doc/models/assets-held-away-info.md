
# Assets Held Away Info

*This model accepts additional fields of type Any.*

## Structure

`AssetsHeldAwayInfo`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `str` | Required | All objects should have Unique names |
| `expected_date_of_liquidity` | `str` | Required | Future date when this asset will convert into assets available for GOE advice |
| `expected_value_at_liquidity` | `float` | Required | Value expected at liquidation date<br><br>**Constraints**: `>= 0` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.assets_held_away_info import AssetsHeldAwayInfo

assets_held_away_info = AssetsHeldAwayInfo(
    name='real-estate',
    expected_date_of_liquidity='01-01-2030',
    expected_value_at_liquidity=300000,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

