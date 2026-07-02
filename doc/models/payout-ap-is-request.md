
# Payout Ap Is Request

*This model accepts additional fields of type unknown.*

## Structure

`PayoutApIsRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client45`](../../doc/models/client-45.md) | Required | - |
| `purpose` | `string` | Required | - |
| `currency` | `string` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PayoutApIsRequest } from 'ps-apimatic-sdk';

const payoutApIsRequest: PayoutApIsRequest = {
  client: {
    email: 'ashishm.21190@gmail.com',
    country: 'MX',
    phone: '+14377717874',
    fullName: 'MARCO ANTONIO FERNANDEZ RAMIREZ',
    stateCode: 'test',
    speiClabe: '012180027944986158',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purpose: 'payout',
  currency: 'MXN',
  payoutMethod: 'PAYOUT-SPEI',
  brandId: '{{merchant_brand_id}}',
  amount: 20,
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

