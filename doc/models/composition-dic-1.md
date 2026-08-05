
# Composition Dic 1

Present value of the particular asset

*This model accepts additional fields of type Any.*

## Structure

`CompositionDic1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `equity` | `float` | Required | % of equity / equity like assets in the asset. All three must add to 1<br><br>**Constraints**: `> 0`, `< 1` |
| `debt` | `float` | Required | % of debt assets in the concerned asset. All three must add to 1<br><br>**Constraints**: `> 0`, `< 1` |
| `other` | `float` | Required | % of any other assets in the asset. All three must add to 1<br><br>**Constraints**: `> 0`, `< 1` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.composition_dic_1 import CompositionDic1

composition_dic_1 = CompositionDic1(
    equity=0.45,
    debt=0.02,
    other=0.53,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

