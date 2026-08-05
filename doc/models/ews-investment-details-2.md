
# Ews Investment Details 2

Contains all common investment details and the investment list.

*This model accepts additional fields of type Any.*

## Structure

`EwsInvestmentDetails2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `curr_date` | `str` | Optional | The current date, same as in RunPipe API. If not given then it takes the current system date. |
| `current_age` | `int` | Required | The current age of the investor.<br><br>**Constraints**: `>= 0` |
| `retirement_age` | `int` | Optional | The retirement age of the investor. |
| `investment_list` | [`List[EwsInvestmentItem]`](../../doc/models/ews-investment-item.md) | Required | The list of investment accounts with their details. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.ews_account_infusion_item import EwsAccountInfusionItem
from goeapi.models.ews_investment_details_2 import EwsInvestmentDetails2
from goeapi.models.ews_investment_item import EwsInvestmentItem
from goeapi.models.infusiontype import Infusiontype

ews_investment_details_2 = EwsInvestmentDetails2(
    current_age=194,
    investment_list=[
        EwsInvestmentItem(
            investment_id='investmentId2',
            lumpsum_amount=66,
            account_infusion=[
                EwsAccountInfusionItem(
                    date='date0',
                    value=99.86,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            end_date='endDate2',
            infusion_type=Infusiontype.MONTHLY,
            funding_type='fundingType4',
            account_type='accountType0',
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    curr_date='currDate0',
    retirement_age=64,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

