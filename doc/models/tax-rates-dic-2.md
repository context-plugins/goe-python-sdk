
# Tax Rates Dic 2

Consists of tax rates applicable pre & post-retirement for the entire household

*This model accepts additional fields of type Any.*

## Structure

`TaxRatesDic2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ltcg_pre_retirement` | `float` | Required | Pre-retirement Long Term Capital Gains tax on profits & qualified dividends due to capital appreciation.                         LTCG is applicable only on taxable accounts.<br><br>**Constraints**: `>= 0`, `<= 1` |
| `ltcg_post_retirement` | `float` | Required | Post-retirement Long Term Capital Gains tax on profits & qualified dividends due to capital appreciation.                         LTCG is applicable only on taxable accounts.<br><br>**Constraints**: `>= 0`, `<= 1` |
| `etr_pre_retirement` | `float` | Required | Pre-retirement Effective tax rate applicable on profits due to: <br>                    Unqualified Dividend <br>                    Interest Income <br>                    Social Security Income <br>                    TDA Withdrawal<br><br>**Constraints**: `>= 0`, `<= 1` |
| `etr_post_retirement` | `float` | Required | Post-retirement Effective tax rate applicable on profits due to: <br>                    Unqualified Dividend <br>                    Interest Income <br>                    Social Security Income <br>                    TDA Withdrawal (including RMD)<br><br>**Constraints**: `>= 0`, `<= 1` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.tax_rates_dic_2 import TaxRatesDic2

tax_rates_dic_2 = TaxRatesDic2(
    ltcg_pre_retirement=0.15,
    ltcg_post_retirement=0.15,
    etr_pre_retirement=0.15,
    etr_post_retirement=0.15,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

