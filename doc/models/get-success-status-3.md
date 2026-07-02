
# Get Success Status 3

*This model accepts additional fields of type unknown.*

## Structure

`GetSuccessStatus3`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payoutId` | `string` | Required | - |
| `client` | [`Client17`](../../doc/models/client-17.md) | Required | - |
| `updatedOn` | `number` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `beneficiaryDetail` | [`BeneficiaryDetail6`](../../doc/models/beneficiary-detail-6.md) | Required | - |
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
import { GetSuccessStatus3 } from 'ps-apimatic-sdk';

const getSuccessStatus3: GetSuccessStatus3 = {
  payoutId: '66838ae86d41e41c10a8656d',
  client: {
    email: 'Yogesh@gmail.com',
    country: 'CA',
    phone: '766533230591',
    fullName: 'Test Person-uk',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1719896808,
  payoutMethod: 'PAYOUT-UPI',
  beneficiaryDetail: {
    upi: 'charles.babbage@okhdfc',
    transferType: 'UPI',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  amountUnit: 'MAJOR',
  amount: 10,
  errorMsg: '',
  purpose: 'test payout',
  createdOn: 1719896808,
  merchantRef: '66838ae86d41e41c10a8656d',
  merchantName: 'newMerchant777',
  status: 'PAYOUT_IN_PROCESS',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1719896808,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'payout_in_process',
      timestamp: 1719896810,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'viewed',
      timestamp: 1719900796,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  viewedOn: 1719900796,
  currency: 'INR',
  paymentOn: 0,
  successCallback: 'https://success.com',
  failureCallback: 'https://failure.com',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

