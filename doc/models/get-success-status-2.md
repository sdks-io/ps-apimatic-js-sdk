
# Get Success Status 2

*This model accepts additional fields of type unknown.*

## Structure

`GetSuccessStatus2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payoutId` | `string` | Required | - |
| `client` | [`Client37`](../../doc/models/client-37.md) | Required | - |
| `updatedOn` | `number` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `beneficiaryDetail` | [`BeneficiaryDetail`](../../doc/models/beneficiary-detail.md) | Required | - |
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
import { GetSuccessStatus2 } from 'ps-apimatic-sdk';

const getSuccessStatus2: GetSuccessStatus2 = {
  payoutId: '6685467c0e5b201a73f91256',
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
  updatedOn: 1720010823,
  payoutMethod: 'PAYOUT-FAWRYPAY',
  beneficiaryDetail: {
    bankAccountNumber: '123456789011',
    upi: 'charles.babbage@okhdfc',
    transferType: 'IMPS',
    ifscCode: 'SBIN0001077',
    payeeName: 'deepak singhal',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  amountUnit: 'MAJOR',
  amount: 20,
  errorMsg: '',
  purpose: 'test payout',
  createdOn: 1720010364,
  merchantRef: '6685467c0e5b201a73f91256',
  merchantName: 'test',
  status: 'PAID',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1720010364,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'payout_in_process',
      timestamp: 1720010367,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'viewed',
      timestamp: 1720010582,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'paid',
      timestamp: 1720010823,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  viewedOn: 1720179568,
  currency: 'EGP',
  paymentOn: 1720010823,
  successCallback: 'https://success.com',
  failureCallback: 'https://failure.com',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

