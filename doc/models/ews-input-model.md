
# Ews Input Model

*This model accepts additional fields of type Any.*

## Structure

`EwsInputModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `goal_profile` | [`EwsGoalProfile`](../../doc/models/ews-goal-profile.md) | Required | - |
| `investment_details` | [`EwsInvestmentDetails2`](../../doc/models/ews-investment-details-2.md) | Required | Contains all common investment details and the investment list. |
| `risk_profile` | [`Riskprofile`](../../doc/models/riskprofile.md) | Required | The risk tolerance profile selected by the user. This is defined at the user level, not per goal. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.ews_account_infusion_item import EwsAccountInfusionItem
from goeapi.models.ews_goal_profile import EwsGoalProfile
from goeapi.models.ews_goal_profile_item import EwsGoalProfileItem
from goeapi.models.ews_input_model import EwsInputModel
from goeapi.models.ews_investment_details_2 import EwsInvestmentDetails2
from goeapi.models.ews_investment_item import EwsInvestmentItem
from goeapi.models.goalfrequency import Goalfrequency
from goeapi.models.goalpriority import Goalpriority
from goeapi.models.infusiontype import Infusiontype
from goeapi.models.riskprofile import Riskprofile
from goeapi.models.scenariotype import Scenariotype

ews_input_model = EwsInputModel(
    goal_profile=EwsGoalProfile(
        goal_profile_list=[
            EwsGoalProfileItem(
                goal_amount=600000,
                goal_start_date='01-01-2028',
                goal_end_date='01-12-2030',
                goal_id='G_1',
                goal_priority=Goalpriority.NEED,
                scenario_type=Scenariotype.RETIREMENT,
                goal_frequency=Goalfrequency.YEARLY,
                bequest_amount=0,
                goal_name='Retirement Living Expenses',
                goal_type='goalType6',
                goal_rank=1,
                current_portfolio_id=228,
                portfolio_set_label='default',
                account_mapping=None,
                additional_properties={
                    'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                }
            ),
            EwsGoalProfileItem(
                goal_amount=550000,
                goal_start_date='01-12-2030',
                goal_end_date='01-12-2030',
                goal_id='G_2',
                goal_priority=Goalpriority.WANT,
                scenario_type=Scenariotype.REGULAR,
                goal_frequency=Goalfrequency.YEARLY,
                bequest_amount=0,
                goal_name='Child\'s College Fund',
                goal_type='goalType6',
                goal_rank=2,
                current_portfolio_id=228,
                portfolio_set_label='default',
                account_mapping=None,
                additional_properties={
                    'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                }
            )
        ],
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    investment_details=EwsInvestmentDetails2(
        current_age=45,
        investment_list=[
            EwsInvestmentItem(
                investment_id='A_1',
                lumpsum_amount=160000,
                account_infusion=[
                    EwsAccountInfusionItem(
                        date='08-01-2026',
                        value=0,
                        additional_properties={
                            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                        }
                    ),
                    EwsAccountInfusionItem(
                        date='01-01-2027',
                        value=180000,
                        additional_properties={
                            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                        }
                    ),
                    EwsAccountInfusionItem(
                        date='01-01-2028',
                        value=180000,
                        additional_properties={
                            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                        }
                    ),
                    EwsAccountInfusionItem(
                        date='01-01-2029',
                        value=180000,
                        additional_properties={
                            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                        }
                    ),
                    EwsAccountInfusionItem(
                        date='01-01-2030',
                        value=180000,
                        additional_properties={
                            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                        }
                    )
                ],
                end_date='01-01-2030',
                infusion_type=Infusiontype.YEARLY,
                funding_type='incomeSources',
                account_type='accountType0',
                additional_properties={
                    'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                }
            )
        ],
        curr_date='08-01-2026',
        retirement_age=134,
        additional_properties={
            'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
        }
    ),
    risk_profile=Riskprofile.AGGRESSIVE,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

