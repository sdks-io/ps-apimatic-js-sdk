
# Create Pay Out Request 6

*This model accepts additional fields of type unknown.*

## Structure

`CreatePayOutRequest6`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client7`](../../doc/models/client-7.md) | Required | - |
| `beneficiaryDetail` | [`BeneficiaryDetail2`](../../doc/models/beneficiary-detail-2.md) | Required | - |
| `purpose` | `string` | Required | - |
| `currency` | `string` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `brandId` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreatePayOutRequest6 } from 'ps-apimatic-sdk';

const createPayOutRequest6: CreatePayOutRequest6 = {
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
  beneficiaryDetail: {
    bankAccountName: 'Rahul Agarwal',
    bankAccountNumber: '645101511808',
    bankCountryCode: 'AT',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purpose: 'Testing payout',
  currency: 'EUR',
  payoutMethod: 'PAYOUT-BANKTRANSFER',
  amount: 10,
  brandId: 'f2f689d5-ca86-4514-94b9-f41bcdf857d7',
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

