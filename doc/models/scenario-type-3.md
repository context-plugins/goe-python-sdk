
# Scenario Type 3

Determines the type of the scenario, the suggested portfolio and the wealth glide path is created accordingly.                                             ‘regular’ for regular goals accumulation goals where cash flows are positive (contributions) and with a typical target wealth                                             ‘retirement’ for scenarios where a decumulation period is included: <br>                                             1.	Scenarios with an accumulation period (and an initial wealth) & positive cash flows followed by a decumulation period with withdrawals (negative cash flows) with or without an inheritance <br>                                             2.	Scenarios with an initial wealth followed by a decumulation period with or without an inheritance

*This model accepts additional fields of type Any.*

## Enumeration

`ScenarioType3`

## Fields

| Name |
|  --- |
| `REGULAR` |
| `RETIREMENT` |

## Example

```python
from goeapi.models.scenario_type_3 import ScenarioType3

scenario_type_3 = ScenarioType3.REGULAR
```

