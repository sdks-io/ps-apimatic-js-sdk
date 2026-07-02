
# Payout Request 2

*This model accepts additional fields of type unknown.*

## Structure

`PayoutRequest2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`MClient`](../../doc/models/m-client.md) | Required | - |
| `purpose` | `string` | Required | - |
| `currency` | `string` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PayoutRequest2 } from 'ps-apimatic-sdk';

const payoutRequest2: PayoutRequest2 = {
  client: {
    email: 'akshaya@gmail.com',
    streetAddress: '10 New Burlington StreetApt. 214',
    city: 'London',
    fullName: 'akshaya singhal',
    zipCode: 'W1S 3BE',
    country: 'CD',
    dateOfBirth: '1994-31-04',
    stateCode: 'RJ',
    phone: '+243999999999',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purpose: 'Testing payout',
  currency: 'CDF',
  payoutMethod: 'PAYOUT-MOBILEMONEY',
  amount: 100,
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

