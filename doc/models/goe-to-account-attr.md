
# Goe to Account Attr

*This model accepts additional fields of type Any.*

## Structure

`GoeToAccountAttr`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_id` | `str` | Required | Used to identify an account |
| `account_type` | `str` | Optional | Defines the type of account given.                    In the case of TDA and Roth accounts, the possible ‘accountType’ are: “401k” and “IRA”.                     In the case of Taxable account, ‘accountType’ does not exist and this field can be passed as null.                     In future releases, the recommendations would be tuned to the ‘accountType’. |
| `taxability_type` | `str` | Required | Defines the nature of the account. <br>                        “T”: taxable account <br>                        “D”: tax deferred account <br>                        “F”: Roth account |
| `member_i_ds` | `List[str]` | Required | List of member IDs that have claim over a single account.                         It is recommended to have an aggregated “taxable” account for all members in the household.                         In casethe case of tda / roth accounts, different members of a household can have different accounts.                         For MVP, exactly one member should be passed in the request payload. |
| `current_balance` | `int` | Required | Account balance as of the current date |
| `current_holdings` | [`List[GoeToCategory]`](../../doc/models/goe-to-category.md) | Required | Details of the holdings in an account |
| `cashflow_details` | [`GoeToCashflowDetails2`](../../doc/models/goe-to-cashflow-details-2.md) | Required | Details of infusions i.e., money deposited in an account |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.goe_to_account_attr import GoeToAccountAttr
from goeapi.models.goe_to_cashflow_details_2 import GoeToCashflowDetails2
from goeapi.models.goe_to_category import GoeToCategory

goe_to_account_attr = GoeToAccountAttr(
    account_id='5',
    taxability_type='T',
    member_i_ds=[
        'memberIDs2',
        'memberIDs3',
        'memberIDs4'
    ],
    current_balance=14589,
    current_holdings=[
        GoeToCategory(
            category_name='CASH',
            category_id='10',
            category_price=1,
            quantity=14589,
            cost_basis=14589,
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    cashflow_details=GoeToCashflowDetails2(
        start_date='01-03-2024',
        end_date='01-11-2032',
        cashflow_amt=[
            237.45
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

