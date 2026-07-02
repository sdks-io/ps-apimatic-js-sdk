
# Create Pay Out Request

*This model accepts additional fields of type unknown.*

## Structure

`CreatePayOutRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client8`](../../doc/models/client-8.md) | Required | - |
| `payoutMethod` | `string` | Required | - |
| `purpose` | `string` | Required | - |
| `currency` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `successRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreatePayOutRequest } from 'ps-apimatic-sdk';

const createPayOutRequest: CreatePayOutRequest = {
  client: {
    email: 'gouridausa+2@gmail.com',
    streetAddress: 'test test',
    city: '123',
    fullName: 'Pay secure',
    zipCode: '234567',
    country: 'CA',
    stateCode: 'CT',
    phone: '1111111111',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  payoutMethod: 'PAYOUT-INTERAC-ETRANSFER',
  purpose: 'entertainment',
  currency: 'CAD',
  amount: 18,
  successRedirect: 'https://success.com',
  failureRedirect: 'https://failure.com',
  pendingRedirect: 'https://pending.com',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

