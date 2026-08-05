
# Category

*This model accepts additional fields of type Any.*

## Structure

`Category`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `category_name` | `str` | Required | Unique name assigned to an asset category in the portfolio |
| `category_id` | `str` | Required | Unique id assigned to an asset category in the portfolio |
| `category_price` | `float` | Required | Price of the security as on the date the request payload is generated.                         For “Cash”, the category Price is assumed to be 1 for the initial call.                         In case of multiple lots within the same category, the average price for the multiple lots is used. |
| `quantity` | `float` | Required | Number of units of the underlying fund <br>                    Note: <br>                    Amount in a security = categoryPrice x quantity |
| `cost_basis` | `float` | Required | The purchase price of the funds. In the case of multiple lots within the same category, the average cost price is used.                     This field is relevant for taxable accounts where gains are computed as following:<br>                    Capital Gains = Market Price - Cost Basis |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.category import Category

category = Category(
    category_name='CASH',
    category_id='10',
    category_price=1,
    quantity=200000,
    cost_basis=14589,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

