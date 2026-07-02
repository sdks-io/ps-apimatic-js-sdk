
# Get Status

*This model accepts additional fields of type unknown.*

## Structure

`GetStatus`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payoutId` | `string` | Required | - |
| `client` | [`Client86`](../../doc/models/client-86.md) | Required | - |
| `updatedOn` | `number` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `beneficiaryDetail` | [`BeneficiaryDetail4`](../../doc/models/beneficiary-detail-4.md) | Required | - |
| `amountUnit` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `errorMsg` | `string` | Required | - |
| `purpose` | `string` | Required | - |
| `createdOn` | `number` | Required | - |
| `merchantRef` | `string` | Required | - |
| `status` | `string` | Required | - |
| `statusHistory` | [`StatusHistory[]`](../../doc/models/status-history.md) | Required | - |
| `currency` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { GetStatus } from 'ps-apimatic-sdk';

const getStatus: GetStatus = {
  payoutId: '65ffadb4c1c83822903a9205',
  client: {
    email: 'customer141@email.uk',
    fullName: 'Test Person-uk',
    streetAddress: 'Random city address',
    country: 'SG',
    city: 'Singapore',
    zipCode: '123456',
    stateCode: 'test',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1711254964,
  payoutMethod: 'Payout-BANKTRANSFER',
  beneficiaryDetail: {
    bankName: 'DBS Bank',
    bankAccountName: 'test test',
    bankAccountCurrency: 'SGD',
    bankAccountNumber: '12345640',
    bankCountryCode: 'SG',
    swiftCode: 'DBSSSGSG',
    routingParam: {
      bankCode: '897678',
      bankBranchCode: '888',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  amountUnit: 'MAJOR',
  amount: 1000,
  errorMsg: 'Currency Account has insufficient balance.',
  purpose: 'test payout',
  createdOn: 1711254972,
  merchantRef: '65ffadb4c1c83822903a9205',
  status: 'ERROR',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1711254964,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'error',
      timestamp: 1711254972,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  currency: 'USD',
  successCallback: 'https://success.com',
  failureCallback: 'https://failure.com',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

