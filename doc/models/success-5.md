
# Success 5

*This model accepts additional fields of type unknown.*

## Structure

`Success5`

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
| `status` | `string` | Required | - |
| `statusHistory` | [`StatusHistory[]`](../../doc/models/status-history.md) | Required | - |
| `currency` | `string` | Required | - |
| `paymentOn` | `number` | Required | - |
| `payOutDetails` | [`PayOutDetails1`](../../doc/models/pay-out-details-1.md) | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success5 } from 'ps-apimatic-sdk';

const success5: Success5 = {
  payoutId: '670cb200fcc7f4706acb6759',
  client: {
    email: 'ashishm.21190@gmail.com',
    country: 'CA',
    phone: '+14377717874',
    fullName: 'Ashish Mistry',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1728885248,
  payoutMethod: 'PAYOUT-INTERAC-REQUEST-MONEY',
  amountUnit: 'MAJOR',
  amount: 1,
  errorMsg: '',
  purpose: 'test payout',
  createdOn: 1728885248,
  merchantRef: '670cb200fcc7f4706acb6759',
  status: 'PAYOUT_IN_PROCESS',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1728885248,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'payout_in_process',
      timestamp: 1728885253,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  currency: 'CAD',
  paymentOn: 0,
  payOutDetails: {
    emailAddress: 'ashishm.21190@gmail.com',
    secretQa: 'q670200747066759362',
    secretAnswer: 'a670200747066759362',
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

