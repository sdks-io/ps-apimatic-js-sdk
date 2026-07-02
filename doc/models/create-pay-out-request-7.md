
# Create Pay Out Request 7

*This model accepts additional fields of type unknown.*

## Structure

`CreatePayOutRequest7`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client17`](../../doc/models/client-17.md) | Required | - |
| `beneficiaryDetail` | [`BeneficiaryDetail5`](../../doc/models/beneficiary-detail-5.md) | Required | - |
| `purpose` | `string` | Required | - |
| `currency` | `string` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreatePayOutRequest7 } from 'ps-apimatic-sdk';

const createPayOutRequest7: CreatePayOutRequest7 = {
  client: {
    email: 'yogesh@gmail.com',
    country: 'CA',
    phone: '766225230591',
    fullName: 'Test Person-uk',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  beneficiaryDetail: {
    upi: 'alpha@bravo',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purpose: 'test payout',
  currency: 'INR',
  payoutMethod: 'PAYOUT-THIRDPARTY-UPI',
  amount: 10,
  successCallback: 'https://success.com',
  failureCallback: 'https://failure.com',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

