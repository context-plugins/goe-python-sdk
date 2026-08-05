
# Goe to Category

*This model accepts additional fields of type Any.*

## Structure

`GoeToCategory`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `category_name` | `str` | Required | Unique name assigned to an asset category in the portfolio |
| `category_id` | `str` | Required | Unique id assigned to an asset category in the portfolio |
| `category_price` | `float` | Required | Price of the security as on the date the request payload is generated.                         For “Cash”, the category Price is assumed to be 1 for the initial call. |
| `quantity` | `float` | Required | Number of units of the underlying fund  <br>                    Note:  <br>                    Amount in a security = categoryPrice x quantity |
| `cost_basis` | `float` | Required | The purchase price of the funds. In the case of multiple lots within the same category, the average cost price is used. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.goe_to_category import GoeToCategory

goe_to_category = GoeToCategory(
    category_name='CASH',
    category_id='10',
    category_price=1,
    quantity=14589,
    cost_basis=14589,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

