
# Household Goe for Taxes Obj 2

contains all information about all the participants.

*This model accepts additional fields of type Any.*

## Structure

`HouseholdGoeForTaxesObj2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `household_id` | `str` | Required | a unique id assigned to the entire household. |
| `state_of_residence` | `str` | Optional | State of residence in United States.                    This is an optional field. |
| `member_list` | [`List[MemberGoeForTaxesObj]`](../../doc/models/member-goe-for-taxes-obj.md) | Required | Contains details about members in the household. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.household_goe_for_taxes_obj_2 import HouseholdGoeForTaxesObj2
from goeapi.models.member_goe_for_taxes_obj import MemberGoeForTaxesObj
from goeapi.models.member_type import MemberType

household_goe_for_taxes_obj_2 = HouseholdGoeForTaxesObj2(
    household_id='house_1',
    member_list=[
        MemberGoeForTaxesObj(
            member_type=MemberType.PRIMARY,
            member_id='1234',
            dob='12-1968',
            current_age=55,
            retirement_age=65,
            current_salary=50000,
            social_security_start_age=62,
            tda_balance_for_rmd=10000,
            rmd_utilized=2000,
            existing_monthly_social_security_amount=1000,
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    state_of_residence='CA',
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

