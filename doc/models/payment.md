
# Payment

*This model accepts additional fields of type unknown.*

## Structure

`Payment`

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
import { Payment } from 'ps-apimatic-sdk';

const payment: Payment = {
  isOutgoing: false,
  paymentType: 'PURCHASE',
  amount: 9,
  currency: 'USD',
  netAmount: 9,
  feeAmount: 10.2591,
  pendingAmount: 0,
  pendingUnfreezeOn: 'pending_unfreeze_on2',
  description: '',
  paidOn: 1690295205,
  remotePaidOn: 1690295205,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

