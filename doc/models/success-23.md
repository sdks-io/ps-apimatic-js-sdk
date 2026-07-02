
# Success 23

*This model accepts additional fields of type unknown.*

## Structure

`Success23`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payoutId` | `string` | Required | - |
| `client` | [`Client7`](../../doc/models/client-7.md) | Required | - |
| `updatedOn` | `number` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `beneficiaryDetail` | [`BeneficiaryDetail3`](../../doc/models/beneficiary-detail-3.md) | Required | - |
| `amountUnit` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `errorMsg` | `string` | Required | - |
| `purpose` | `string` | Required | - |
| `createdOn` | `number` | Required | - |
| `merchantRef` | `string` | Required | - |
| `status` | `string` | Required | - |
| `statusHistory` | [`StatusHistory[]`](../../doc/models/status-history.md) | Required | - |
| `currency` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success23 } from 'ps-apimatic-sdk';

const success23: Success23 = {
  payoutId: '65ffadb4c1c83822903a9205',
  client: {
    email: 'rahul@gmail.com',
    country: 'DE',
    city: 'Zurich',
    stateCode: 'QLD',
    fullName: 'Test test',
    streetAddress: '10 New Burlington Street Apt. 214',
    zipCode: 'W1S 3BE',
    phone: '+448839471521',
    gender: 'M',
    dateOfBirth: '1970-07-10',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1711254964,
  payoutMethod: 'Payout-BANKTRANSFER',
  beneficiaryDetail: {
    bankAccountName: 'Rahul Agarwal',
    bankAccountNumber: '645101511808',
    bankName: 'ICICI Bank',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  amountUnit: 'MAJOR',
  amount: 10,
  errorMsg: 'Currency Account has insufficient balance.',
  purpose: 'test payout',
  createdOn: 1711254972,
  merchantRef: '65ffadb4c1c83822903a9205',
  status: 'PAID',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1711254964,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'paid',
      timestamp: 1711254972,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  currency: 'EUR',
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

