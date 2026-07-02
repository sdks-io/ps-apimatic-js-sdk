
# Settlement

*This model accepts additional fields of type unknown.*

## Structure

`Settlement`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `settlementId` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `currency` | `string` | Required | - |
| `status` | `string` | Required | - |
| `settledOn` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Settlement } from 'ps-apimatic-sdk';

const settlement: Settlement = {
  settlementId: '1234',
  amount: 100,
  currency: 'USD',
  status: 'settled',
  settledOn: -41795,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

