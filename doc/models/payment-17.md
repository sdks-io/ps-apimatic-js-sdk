
# Payment 17

*This model accepts additional fields of type unknown.*

## Structure

`Payment17`

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
import { Payment17 } from 'ps-apimatic-sdk';

const payment17: Payment17 = {
  isOutgoing: false,
  paymentType: 'PURCHASE',
  amount: 5.86,
  currency: 'USD',
  netAmount: 5.86,
  feeAmount: 0,
  pendingAmount: 0,
  pendingUnfreezeOn: 'pending_unfreeze_on6',
  description: '',
  paidOn: 1752485524,
  remotePaidOn: 1752485524,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

