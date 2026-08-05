
# Household 2

contains all information about all the participants within the household.                         For MVP, only a single member is allowed.

*This model accepts additional fields of type Any.*

## Structure

`Household2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `household_id` | `str` | Required | a unique id assigned to the entire household. |
| `state_of_residence` | `str` | Optional | State of residence in United States.                     This is an optional field. |
| `member_list` | [`List[Member]`](../../doc/models/member.md) | Required | Contains details about members in the household. <br>            Note: <br>            For MVP, exactly one member is allowed in the household. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.household_2 import Household2
from goeapi.models.member import Member
from goeapi.models.member_type_1 import MemberType1

household_2 = Household2(
    household_id='house_1',
    member_list=[
        Member(
            member_type=MemberType1.PRIMARY,
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

