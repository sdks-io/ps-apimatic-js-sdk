
# Aggregated Balance

*This model accepts additional fields of type unknown.*

## Structure

`AggregatedBalance`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currency` | `string` | Required | - |
| `balance` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { AggregatedBalance } from 'ps-apimatic-sdk';

const aggregatedBalance: AggregatedBalance = {
  currency: 'CAD',
  balance: 1616.76,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

