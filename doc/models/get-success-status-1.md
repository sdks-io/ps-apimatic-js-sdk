
# Get Success Status 1

*This model accepts additional fields of type unknown.*

## Structure

`GetSuccessStatus1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payoutId` | `string` | Required | - |
| `client` | [`Client17`](../../doc/models/client-17.md) | Required | - |
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
| `payOutDetails` | [`PayOutDetails1`](../../doc/models/pay-out-details-1.md) | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { GetSuccessStatus1 } from 'ps-apimatic-sdk';

const getSuccessStatus1: GetSuccessStatus1 = {
  payoutId: '670926784600a76f8d8a1b43',
  client: {
    email: 'ashishm.21190@gmail.com',
    country: 'CA',
    phone: '+14377717874',
    fullName: 'Ashish Mistry',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1728653103,
  payoutMethod: 'PAYOUT-INTERAC-DEBIT',
  amountUnit: 'MAJOR',
  amount: 1,
  errorMsg: '',
  purpose: 'test payout',
  createdOn: 1728652920,
  merchantRef: '670926784600a76f8d8a1b43',
  merchantName: 'Ajay002',
  status: 'PAID',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1728652920,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'payout_in_process',
      timestamp: 1728652924,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'paid',
      timestamp: 1728653103,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'viewed',
      timestamp: 1729154507,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  viewedOn: 1729154507,
  currency: 'CAD',
  paymentOn: 1728653103,
  payOutDetails: {
    emailAddress: 'ashishm.21190@gmail.com',
    secretQa: 'q6709267846007688143362',
    secretAnswer: 'a6709267846007688143362',
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

