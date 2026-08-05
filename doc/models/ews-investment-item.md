
# Ews Investment Item

*This model accepts additional fields of type Any.*

## Structure

`EwsInvestmentItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `investment_id` | `str` | Required | Unique identifier for the investment account. |
| `funding_type` | `str` | Optional | Funding type label for the account. |
| `account_type` | `str` | Optional | Type of accounts used to map accounts to the goals. |
| `lumpsum_amount` | `int` | Required | The initial investment amount available as of the current date.<br><br>**Constraints**: `>= 0` |
| `account_infusion` | [`List[EwsAccountInfusionItem]`](../../doc/models/ews-account-infusion-item.md) | Required | Contains scheduled future contributions with their dates and amounts |
| `end_date` | `str` | Required | The end date of the investment account. |
| `infusion_type` | [`Infusiontype`](../../doc/models/infusiontype.md) | Required | Specifies the frequency at which account contributions occur. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.ews_account_infusion_item import EwsAccountInfusionItem
from goeapi.models.ews_investment_item import EwsInvestmentItem
from goeapi.models.infusiontype import Infusiontype

ews_investment_item = EwsInvestmentItem(
    investment_id='investmentId4',
    lumpsum_amount=38,
    account_infusion=[
        EwsAccountInfusionItem(
            date='date0',
            value=99.86,
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    end_date='endDate0',
    infusion_type=Infusiontype.MONTHLY,
    funding_type='fundingType6',
    account_type='accountType8',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

