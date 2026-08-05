
# Member

*This model accepts additional fields of type Any.*

## Structure

`Member`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `member_type` | [`MemberType1`](../../doc/models/member-type-1.md) | Required | Usually, a higher earning member is assigned as “Primary” member.                     Does not impact any computation. |
| `member_id` | `str` | Required | Identifier unique to each member of the household             Does not impact any computation. |
| `dob` | `str` | Required | Date of birth of a member in the household.                     Important for Social Security, RMD, and early withdrawal penalties.                     Valid Date Format: 'MM-YYYY'. |
| `current_age` | `int` | Required | Current age of the household member |
| `retirement_age` | `int` | Required | Retirement age of the household member |
| `current_salary` | `float` | Required | Current salary of the household member.                         Used for Social Security calculations |
| `social_security_start_age` | `int` | Required | Custom age at which the member wishes to receive her Social Security benefits |
| `tda_balance_for_rmd` | `float` | Optional | Optional field.                    If the RMD needs to be computed in the current financial year |
| `rmd_utilized` | `float` | Optional | Optional field.             In the event the RMD computations are desired for the current financial year,                 this field specifies the amount of RMD already taken out before the GOE call was made. |
| `existing_monthly_social_security_amount` | `float` | Optional | In the event when the user is already receiving the SS amount and             their ‘currentAge’ is greater than the ‘socialSecurityStartAge’, , this field needs to have existing Social Security.             Otherwise, the field can be set as null. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.member import Member
from goeapi.models.member_type_1 import MemberType1

member = Member(
    member_type=MemberType1.PRIMARY,
    member_id='1234',
    dob='01-1973',
    current_age=55,
    retirement_age=65,
    current_salary=100000,
    social_security_start_age=62,
    tda_balance_for_rmd=79.5,
    rmd_utilized=115.94,
    existing_monthly_social_security_amount=208.82,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

