
# Goe with Annuities Input Model

*This model accepts additional fields of type Any.*

## Structure

`GoeWithAnnuitiesInputModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `include_annuities` | `bool` | Required | Flag to recommend allocation to annuities. |
| `annuity_type` | `str` | Required, Constant | Type of annuity. [non-functional]<br><br>**Value**: `"deferred"` |
| `annuity_price` | [`List[AnnuityPrice]`](../../doc/models/annuity-price.md) | Optional | Annuity price series         Mandatory only if includeAnnuities is true.         For a deferred annuity - complete age year rate         table to be passed covering all ages from        current age to retirement age. This rate determines the monthly payout. |
| `date_of_birth` | `str` | Required | Participant’s date of birth.<br>            Accepts date in dd-mm-yyyy & mm-yyyy format. |
| `retirement_age` | `int` | Required | Participant’s retirement age. <br>            Accepts positive numbers only.<br><br>**Constraints**: `> 0` |
| `drawdown_age` | `int` | Required | Participant’s drawdown age. <br>            Accepts positive numbers, greater than or equal to the retirementAge.<br><br>**Constraints**: `> 0` |
| `planning_age` | `int` | Required | Age of last withdrawal. <br>            Accepts positive numbers, greater than the drawdownAge.<br><br>**Constraints**: `> 0` |
| `current_salary` | `float` | Required | Participant’s current salary. <br>            Accepts positive numbers with up to 2 decimal places. Should always be passed as annual income.<br><br>**Constraints**: `>= 0` |
| `total_account_balance` | `float` | Required | Total balance in the account. <br>            Valid values: positive numbers with up to 2 decimal places.<br><br>**Constraints**: `>= 0` |
| `periodic_contributions` | `float` | Required | Periodic contribution amount.<br>            Valid values: positive numbers with up to 2 decimal places. Represented as a dollar value.<br><br>**Constraints**: `>= 0` |
| `contribution_freq` | [`ContributionFreq`](../../doc/models/contribution-freq.md) | Required | Frequency of the periodic contributions. |
| `current_annuity_balance` | `float` | Optional | Current balance of annuity assets.<br>            Valid values: positive numbers with up to 2 decimal places. <br>                 Only one of annuityBalance or annuityIncome can be sent,                     both cannot have values, one needs to be “null”.<br><br>**Constraints**: `>= 0` |
| `current_annuity_income` | `float` | Optional | Current accumulated yearly income from annuity as of the             drawdown age. <br>            Valid values: positive numbers with up to 2 decimal places. <br>                 Only one of annuityBalance or annuityIncome can be sent,                     both cannot have values, one needs to be “null”.<br><br>**Constraints**: `>= 0` |
| `retirement_income_goal` | `float` | Optional | Total yearly retirement income goal for the participant.<br>            Valid values: positive numbers with up to 2 decimal places.<br><br>**Constraints**: `>= 0` |
| `drawdown_age_ss` | `int` | Optional | Participant’s social security drawdown age. <br>            Valid values: positive whole numbers, greater than or equal to retirement age. |
| `income_from_ss` | `float` | Optional | Total yearly income from the participant from social security. <br>            Valid inputs: positive numbers with up to 2 decimal places.<br><br>**Default**: `0`<br><br>**Constraints**: `>= 0` |
| `outside_assets` | `float` | Required | Total balance in outside assets <br>        Valid inputs: positive numbers with up to 2 decimal places.<br><br>**Constraints**: `>= 0` |
| `other_income` | `float` | Optional | Income from other sources. This is the sum of income from DB and             other annuities. <br>            Valid inputs: positive numbers with up to 2 decimal places.<br>                Should always be passed as annual income.<br><br>**Constraints**: `>= 0` |
| `current_portfolio_id` | `int` | Required | Current portfolio ID to which the wealth is allocated. If GOE             is being called for the first time, this should be null. [non-functional] <br>            Valid inputs: null or positive integers. |
| `calculate_retirement_income_goal` | `bool` | Optional | Flag to ask GOE to calculate the retirement income goal |
| `current_date` | `str` | Required | Participant’s current date. <br>            Valid input: date in dd-mm-yyyy format |
| `risk_profile` | [`RiskProfile4`](../../doc/models/risk-profile-4.md) | Required | Participant’s risk profile. |
| `other_guaranteed_income` | `float` | Required | Income from other guaranteed income sources. <br>            Valid inputs are numbers with up to 2 decimal places.<br><br>**Constraints**: `>= 0` |
| `reallocate` | `bool` | Required | Flag to ask GOE with Annuities to send updated portfolio advice. Sent as true when new advice is needed, else sent as false |
| `fixed_discretionary_split` | `float` | Optional | Proportion of the fixed expenses as a proportion of total goal. Valid inputs up to 4 decimal places<br><br>**Constraints**: `>= 0`, `<= 1` |
| `plan_id` | `str` | Optional | Plan ID of the participant. |
| `participant_id` | `str` | Optional | ID of the participant. |
| `policy` | [`List[PolicyDetails]`](../../doc/models/policy-details.md) | Optional | Contains details about the policy validation associated with the Platform Partner. In this example,             the array includes participantType and callType, however, the dictionary is open and Platform Partners are able to send other fields to define their respective API Policy. |
| `user_input_update` | `bool` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.annuity_price import AnnuityPrice
from goeapi.models.contribution_freq import ContributionFreq
from goeapi.models.goe_with_annuities_input_model import GoeWithAnnuitiesInputModel
from goeapi.models.risk_profile_4 import RiskProfile4
from goeapi.models.value import Value

goe_with_annuities_input_model = GoeWithAnnuitiesInputModel(
    include_annuities=True,
    date_of_birth='01-01-1981',
    retirement_age=61,
    drawdown_age=66,
    planning_age=82,
    current_salary=350000,
    total_account_balance=1260000,
    periodic_contributions=8750,
    contribution_freq=ContributionFreq.MONTHLY,
    outside_assets=210000,
    current_portfolio_id=None,
    current_date='01-01-2024',
    risk_profile=RiskProfile4.AGGRESSIVE,
    other_guaranteed_income=100,
    reallocate=False,
    user_input_update=False,
    annuity_price=[
        AnnuityPrice(
            age=43,
            value=[
                Value(
                    year=2024,
                    rate=120,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=44,
            value=[
                Value(
                    year=2025,
                    rate=115,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=45,
            value=[
                Value(
                    year=2026,
                    rate=110,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=46,
            value=[
                Value(
                    year=2027,
                    rate=105,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=47,
            value=[
                Value(
                    year=2028,
                    rate=100,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=48,
            value=[
                Value(
                    year=2029,
                    rate=95,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=49,
            value=[
                Value(
                    year=2030,
                    rate=90,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=50,
            value=[
                Value(
                    year=2031,
                    rate=85,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=51,
            value=[
                Value(
                    year=2032,
                    rate=80,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=52,
            value=[
                Value(
                    year=2033,
                    rate=75,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=53,
            value=[
                Value(
                    year=2034,
                    rate=70,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=54,
            value=[
                Value(
                    year=2035,
                    rate=65,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=55,
            value=[
                Value(
                    year=2036,
                    rate=64,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=56,
            value=[
                Value(
                    year=2037,
                    rate=63,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=57,
            value=[
                Value(
                    year=2038,
                    rate=62,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=58,
            value=[
                Value(
                    year=2039,
                    rate=61,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=59,
            value=[
                Value(
                    year=2040,
                    rate=60,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=60,
            value=[
                Value(
                    year=2041,
                    rate=59,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        ),
        AnnuityPrice(
            age=61,
            value=[
                Value(
                    year=2042,
                    rate=58,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    current_annuity_balance=35000,
    current_annuity_income=101.6,
    retirement_income_goal=25000,
    drawdown_age_ss=64,
    income_from_ss=10000,
    other_income=25000,
    calculate_retirement_income_goal=False,
    additional_properties={
        'balanceProportion': jsonpickle.decode('0.1'),
        'currAge': jsonpickle.decode('43'),
        'jobTenure': jsonpickle.decode('31'),
        'maritalStatus': jsonpickle.decode('"married"'),
        'spousalSalary': jsonpickle.decode('250000')
    }
)
```

