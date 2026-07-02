
# Pay Out Request

*This model accepts additional fields of type unknown.*

## Structure

`PayOutRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client7`](../../doc/models/client-7.md) | Required | - |
| `purpose` | `string` | Required | - |
| `currency` | `string` | Required | - |
| `merchantRef` | `string` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `extraParam` | [`ExtraParam`](../../doc/models/extra-param.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PayOutRequest } from 'ps-apimatic-sdk';

const payOutRequest: PayOutRequest = {
  client: {
    email: 'rahul@gmail.com',
    country: 'GB',
    city: 'London',
    stateCode: 'QLD',
    fullName: 'Rahul Jain',
    streetAddress: '10 New Burlington Street Apt. 214',
    zipCode: 'W1S 3BE',
    phone: '+44 9876543210',
    gender: 'M',
    dateOfBirth: '1970-07-10',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purpose: 'Testing cards payout',
  currency: 'GBP',
  merchantRef: 'YOUR ORDER ID',
  payoutMethod: 'PAYOUT-CARDS',
  amount: 100,
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  extraParam: {
    cardNumber: '5431240006334004',
    cardHolderName: 'Rahul Agarwal',
    expiryYear: '2030',
    expiryMonth: '11',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

