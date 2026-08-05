
# Account

*This model accepts additional fields of type Any.*

## Structure

`Account`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_id` | `str` | Required | Used to identify an account |
| `account_type` | `str` | Optional | In the case of TDA and Roth accounts, the possible ‘accountType’ are: “401k” and “IRA”.                     In the case of Taxable account, ‘accountType’ does not exist and this field can be passed as null. |
| `taxability_type` | `str` | Required | Defines the nature of the account.<br>                        “T”: taxable account <br>                        “D”: tax deferred account <br>                        “F”: Roth account |
| `member_i_ds` | `List[str]` | Required | List of member IDs that have claim over a single account.                     For MVP, exactly one member should be passed in the request payload. |
| `current_balance` | `float` | Required | Account balance as of the current date |
| `current_holdings` | [`List[Category]`](../../doc/models/category.md) | Required | Details of the holdings in an account |
| `cashflow_details` | [`CashflowDetails2`](../../doc/models/cashflow-details-2.md) | Required | Details of infusions i.e., money deposited in an account |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.account import Account
from goeapi.models.cashflow_details_2 import CashflowDetails2
from goeapi.models.category import Category

account = Account(
    account_id='5',
    taxability_type='T',
    member_i_ds=[
        'memberIDs0',
        'memberIDs1',
        'memberIDs2'
    ],
    current_balance=14589,
    current_holdings=[
        Category(
            category_name='CASH',
            category_id='10',
            category_price=1,
            quantity=200000,
            cost_basis=14589,
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    cashflow_details=CashflowDetails2(
        start_date='01-03-2024',
        end_date='01-11-2032',
        cashflow_amt=[
            2500,
            2575
        ],
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    account_type='401k',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

