
# Cashflow Details 2

Details of infusions i.e., money deposited in an account

*This model accepts additional fields of type Any.*

## Structure

`CashflowDetails2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `start_date` | `str` | Required | The date associated with the first infusion in the account.                     Valid Date Format: 'DD-MM-YYYY' |
| `end_date` | `str` | Required | The date corresponding to the last infusion in the account. |
| `cashflow_amt` | `List[float]` | Optional | List of infusions associated with an account.             The first element of the list denotes the infusion as on “startDate”. The last element corresponds to infusion on the “endDate”.             The start date should be greater current date. If there is an infusion on the current date, it is accounted for in the currentBalance field.             Important: <br>            All infusions b/w “startDate” and “endDate” are assumed to occur, yearly, on the “cashflowDate”. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.cashflow_details_2 import CashflowDetails2

cashflow_details_2 = CashflowDetails2(
    start_date='01-03-2024',
    end_date='01-11-2032',
    cashflow_amt=[
        2500,
        2575
    ],
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

