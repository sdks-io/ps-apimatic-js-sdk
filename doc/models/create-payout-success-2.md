
# Create Payout Success 2

*This model accepts additional fields of type unknown.*

## Structure

`CreatePayoutSuccess2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payoutId` | `string` | Required | - |
| `client` | [`Client37`](../../doc/models/client-37.md) | Required | - |
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
| `payOutDetails` | [`PayOutDetails3`](../../doc/models/pay-out-details-3.md) | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreatePayoutSuccess2 } from 'ps-apimatic-sdk';

const createPayoutSuccess2: CreatePayoutSuccess2 = {
  payoutId: '6687d86dde5d5c0feecf7621',
  client: {
    email: 'test@gmail.com',
    country: 'EG',
    phone: '9586445444',
    fullName: 'Test Person-uk',
    documentId: '29206260104051',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1720178797,
  payoutMethod: 'PAYOUT-FAWRYPAY',
  amountUnit: 'MAJOR',
  amount: 20,
  errorMsg: '',
  purpose: 'test payout',
  createdOn: 1720178797,
  merchantRef: '6687d86dde5d5c0feecf7621',
  status: 'PAYOUT_IN_PROCESS',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1720178797,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'payout_in_process',
      timestamp: 1720178799,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  currency: 'EGP',
  paymentOn: 0,
  payOutDetails: {
    instruction: 'Please use transaction reference 20514294 with the BTC 77361 at any Fawry store to get cashout within 72 hrs',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  successCallback: 'https://success.com',
  failureCallback: 'https://failure.com',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

