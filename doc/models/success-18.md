
# Success 18

*This model accepts additional fields of type unknown.*

## Structure

`Success18`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payoutId` | `string` | Required | - |
| `client` | [`Client68`](../../doc/models/client-68.md) | Required | - |
| `updatedOn` | `number` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `amountUnit` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `errorMsg` | `string` | Required | - |
| `purpose` | `string` | Required | - |
| `createdOn` | `number` | Required | - |
| `merchantRef` | `string` | Required | - |
| `status` | `string` | Required | - |
| `statusHistory` | [`StatusHistory[]`](../../doc/models/status-history.md) | Required | - |
| `currency` | `string` | Required | - |
| `paymentOn` | `number` | Required | - |
| `taxAmount` | `number` | Required | - |
| `taxPercent` | `number` | Required | - |
| `redirectType` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success18 } from 'ps-apimatic-sdk';

const success18: Success18 = {
  payoutId: '683d6fee57aff00ab5faf3c6',
  client: {
    customerId: 'NA',
    email: 'akshayadeepsinghal@gmail.com',
    phone: '+11111111',
    fullName: 'PAYOUT USER',
    country: 'AU',
    stateCode: 'test',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1748856814,
  payoutMethod: 'PAYOUT-PAYID',
  amountUnit: 'MAJOR',
  amount: 1,
  errorMsg: '',
  purpose: 'test payout',
  createdOn: 1748856814,
  merchantRef: '683d6fee57aff00ab5faf3c6',
  status: 'PAID',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1748856814,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'paid',
      timestamp: 1748856816,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  currency: 'AUD',
  paymentOn: 1748856816,
  taxAmount: 0,
  taxPercent: 0,
  redirectType: 'POST',
  successCallback: '<https://success.com>',
  failureCallback: '<https://failure.com>',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

