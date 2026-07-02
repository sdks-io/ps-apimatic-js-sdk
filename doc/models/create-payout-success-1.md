
# Create Payout Success 1

*This model accepts additional fields of type unknown.*

## Structure

`CreatePayoutSuccess1`

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
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreatePayoutSuccess1 } from 'ps-apimatic-sdk';

const createPayoutSuccess1: CreatePayoutSuccess1 = {
  payoutId: '67efc0586720dd3a164fe8b3',
  client: {
    customerId: 'NA',
    email: 'ashishm.21190@gmail.com',
    phone: '+14377717874',
    fullName: 'Test Person-uk',
    country: 'CA',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1743765592,
  payoutMethod: 'PAYOUT-INTERAC-EXPRESS',
  amountUnit: 'MAJOR',
  amount: 10,
  errorMsg: '',
  purpose: 'test payout',
  createdOn: 1743765592,
  merchantRef: '67efc0586720dd3a164fe8b3',
  merchantName: 'arunsinghal',
  status: 'PAID',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1743765592,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'paid',
      timestamp: 1743765610,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'viewed',
      timestamp: 1744025266,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  viewedOn: 1744026844,
  currency: 'CAD',
  paymentOn: 1743765610,
  successCallback: 'https://success.com',
  failureCallback: 'https://failure.com',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

