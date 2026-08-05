
# Cashflow Recommendation 1

Cashflow recommendation is at the plan level.Note: -               Empty in case plan meets the target probability.

*This model accepts additional fields of type Any.*

## Structure

`CashflowRecommendation1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cash_flow_monthly` | `float` | Required | Suggested monthly cashflow amount that aims to improve the plan probability to meet the target probability.                Note: - Empty in case of yearly infusions. |
| `cash_flow_yearly` | `float` | Required | Suggested yearly cashflow amount that aims to improve the plan probability to meet the target probability.            Note: - Empty in case of monthly infusions. |
| `start_date` | `str` | Required | Suggested start date of the cashflows considering cashflow recommendation. |
| `end_date` | `str` | Required | Suggested end date of the cashflows considering cashflow recommendation. |
| `new_plan_prob` | `float` | Required | New plan probability as per the suggested tenure recommendation. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example

```python
import jsonpickle

from goeapi.models.cashflow_recommendation_1 import CashflowRecommendation1

cashflow_recommendation_1 = CashflowRecommendation1(
    cash_flow_monthly=None,
    cash_flow_yearly=2503,
    start_date='01-01-2022',
    end_date='01-01-2036',
    new_plan_prob=0.85,
    additional_properties={
        'exampleAdditionalProperty': jsonpickle.decode('{"key1":"val1","key2":"val2"}')
    }
)
```

