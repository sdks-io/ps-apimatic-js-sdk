
# Payment 4

*This model accepts additional fields of type unknown.*

## Structure

`Payment4`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `isOutgoing` | `boolean` | Required | - |
| `paymentType` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `currency` | `string` | Required | - |
| `netAmount` | `number` | Required | - |
| `feeAmount` | `number` | Required | - |
| `pendingAmount` | `number` | Required | - |
| `pendingUnfreezeOn` | `string \| null` | Required | - |
| `description` | `string` | Required | - |
| `paidOn` | `number` | Required | - |
| `remotePaidOn` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Payment4 } from 'ps-apimatic-sdk';

const payment4: Payment4 = {
  isOutgoing: false,
  paymentType: 'PURCHASE',
  amount: 1,
  currency: 'CAD',
  netAmount: 1,
  feeAmount: 0,
  pendingAmount: 0,
  pendingUnfreezeOn: 'pending_unfreeze_on8',
  description: '',
  paidOn: 1737549663,
  remotePaidOn: 1737549663,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

