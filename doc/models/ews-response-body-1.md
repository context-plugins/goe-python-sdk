
# Ews Response Body 1

Main response payload

*This model accepts additional fields of type Any.*

## Structure

`EwsResponseBody1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `goal_response_list` | [`List[EwsGoalResponseItem]`](../../doc/models/ews-goal-response-item.md) | Required | List of all goal-level results |
| `account_response_list` | [`List[EwsAccountResponseItem]`](../../doc/models/ews-account-response-item.md) | Required | Account-level allocation results. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.ews_account_response_item import EwsAccountResponseItem
from goeapi.models.ews_goal_response_item import EwsGoalResponseItem
from goeapi.models.ews_goal_split_infusion_item import EwsGoalSplitInfusionItem
from goeapi.models.ews_goal_split_lumpsum_item import EwsGoalSplitLumpsumItem
from goeapi.models.ews_response_body_1 import EwsResponseBody1
from goeapi.models.ews_series_value import EwsSeriesValue
from goeapi.models.fundedstatus import Fundedstatus

ews_response_body_1 = EwsResponseBody1(
    goal_response_list=[
        EwsGoalResponseItem(
            goal_id='goalId8',
            current_wealth=90.22,
            infusions=[
                EwsSeriesValue(
                    value=7.58,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            goal_priority_order=2,
            goal_amount=197.04,
            funded_status=Fundedstatus.FUNDED,
            additional_properties={
                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
            }
        )
    ],
    account_response_list=[
        EwsAccountResponseItem(
            investment_id='investmentId2',
            goal_split_infusion=[
                EwsGoalSplitInfusionItem(
                    goal_id='goalId8',
                    cashflow=[
                        EwsSeriesValue(
                            value=150.28,
                            additional_properties={
                                'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                            }
                        )
                    ],
                    first_contribution_date='firstContributionDate0',
                    first_contribution_amount=44,
                    additional_properties={
                        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
                    }
                )
            ],
            goal_split_lumpsum=[
                EwsGoalSplitLumpsumItem(
                    goal_id='goalId0',
                    value=109.98,
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
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

