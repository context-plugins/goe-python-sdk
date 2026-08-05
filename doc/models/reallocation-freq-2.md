
# Reallocation Freq 2

Describes the frequency of re-allocation. If set to 'yearly',             GOE would assume the re-allocation to happen once a year.                Response parameters such as portfolio path and wealth path would have one value each year.

*This model accepts additional fields of type Any.*

## Enumeration

`ReallocationFreq2`

## Fields

| Name |
|  --- |
| `YEARLY` |
| `HALFYEARLY` |
| `QUARTERLY` |

## Example

```python
from goeapi.models.reallocation_freq_2 import ReallocationFreq2

reallocation_freq_2 = ReallocationFreq2.HALFYEARLY
```

