
# Fixed Asset

*This model accepts additional fields of type Any.*

## Structure

`FixedAsset`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `str` | Required | All objects should have Unique names |
| `current_value` | `float` | Required | Present value of the particular asset.<br><br>**Constraints**: `>= 0` |
| `current_composition` | [`CompositionDic1`](../../doc/models/composition-dic-1.md) | Required | Present value of the particular asset |
| `expected_date_of_conversion_to_aum` | `str` | Required | Future date when this asset will convert into assets available for GOE advice. <br>             Must be in dd-mm-yyyy format |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.composition_dic_1 import CompositionDic1
from goeapi.models.fixed_asset import FixedAsset

fixed_asset = FixedAsset(
    name='Aha-1',
    current_value=75000,
    current_composition=CompositionDic1(
        equity=0.45,
        debt=0.02,
        other=0.53,
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    expected_date_of_conversion_to_aum='23-08-2025',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

