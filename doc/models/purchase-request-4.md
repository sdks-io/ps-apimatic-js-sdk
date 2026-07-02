
# Purchase Request 4

*This model accepts additional fields of type unknown.*

## Structure

`PurchaseRequest4`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client65`](../../doc/models/client-65.md) | Required | - |
| `purchase` | [`Purchase52`](../../doc/models/purchase-52.md) | Required | - |
| `status` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `skipCapture` | `boolean` | Required | - |
| `merchantRef` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PurchaseRequest4 } from 'ps-apimatic-sdk';

const purchaseRequest4: PurchaseRequest4 = {
  client: {
    email: 'example@paysecure.net',
    country: 'IN',
    city: '123',
    stateCode: 'ca',
    streetAddress: 'test test',
    zipCode: '234567',
    phone: '+91 9999999999',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    products: [
      {
        name: 'dk',
        price: '10',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  status: 'created',
  brandId: 'bd69e8a5-adcf-40de-9e43-2b87cb129a5e',
  skipCapture: true,
  merchantRef: 'd9db7ec0-f94c-4a9d-8883-54c19c222d81',
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

