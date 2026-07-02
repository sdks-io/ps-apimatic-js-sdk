
# Pay Out Request 1

*This model accepts additional fields of type unknown.*

## Structure

`PayOutRequest1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client8`](../../doc/models/client-8.md) | Required | - |
| `beneficiaryDetail` | [`BeneficiaryDetail1`](../../doc/models/beneficiary-detail-1.md) | Required | - |
| `payoutMethod` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `currency` | `string` | Required | - |
| `purpose` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PayOutRequest1 } from 'ps-apimatic-sdk';

const payOutRequest1: PayOutRequest1 = {
  client: {
    email: 'customer141@gmail.com',
    streetAddress: 'Vaishali Nagar',
    city: 'Jaipur',
    fullName: 'Rahul Jain',
    zipCode: '302018',
    country: 'IN',
    stateCode: 'RJ',
    phone: '+91 9634088651',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  beneficiaryDetail: {
    bankAccountName: 'Rahul Jain',
    bankAccountNumber: '123456789012',
    ifscCode: 'HDFC021212',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  payoutMethod: 'Payout-BANKTRANSFER',
  brandId: '{{merchant_brand_id}}',
  amount: 100,
  currency: 'INR',
  purpose: 'payout for testing',
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

