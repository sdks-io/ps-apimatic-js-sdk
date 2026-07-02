
# Get Success Status

*This model accepts additional fields of type unknown.*

## Structure

`GetSuccessStatus`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payoutId` | `string` | Required | - |
| `client` | [`Client13`](../../doc/models/client-13.md) | Required | - |
| `updatedOn` | `number` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `amountUnit` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `errorMsg` | `string` | Required | - |
| `purpose` | `string` | Required | - |
| `createdOn` | `number` | Required | - |
| `merchantRef` | `string` | Required | - |
| `merchantName` | `string` | Required | - |
| `status` | `string` | Required | - |
| `statusHistory` | [`StatusHistory[]`](../../doc/models/status-history.md) | Required | - |
| `viewedOn` | `number` | Required | - |
| `currency` | `string` | Required | - |
| `paymentOn` | `number` | Required | - |
| `payOutDetails` | [`PayOutDetails`](../../doc/models/pay-out-details.md) | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { GetSuccessStatus } from 'ps-apimatic-sdk';

const getSuccessStatus: GetSuccessStatus = {
  payoutId: '66bf2e76e3defc36cd575481',
  client: {
    customerId: 'NA',
    email: 'ashishm.21190@gmail.com',
    phone: '+14377717874',
    fullName: 'Ashish Mistry',
    country: 'CA',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1723805728,
  payoutMethod: 'PAYOUT-INTERAC-ETRANSFER',
  amountUnit: 'MAJOR',
  amount: 12,
  errorMsg: '',
  purpose: 'test payout',
  createdOn: 1723805302,
  merchantRef: '66bf2e76e3defc36cd575481',
  merchantName: 'arunsinghal',
  status: 'PAID',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1723805302,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'payout_in_process',
      timestamp: 1723805310,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'paid',
      timestamp: 1723805728,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'viewed',
      timestamp: 1738750221,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  viewedOn: 1738750221,
  currency: 'USD',
  paymentOn: 1723805728,
  payOutDetails: {
    name: 'INTERAC E-TRANSFER',
    emailAddress: 'ashishm.21190@gmail.com',
    secretQa: 'q66276336575481202',
    secretAnswer: 'a66276336575481202',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  successCallback: 'https://webhook.site/d7660184-d724-480c-bad0-cf0480f5518e',
  failureCallback: 'https://webhook.site/d7660184-d724-480c-bad0-cf0480f5518e',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

