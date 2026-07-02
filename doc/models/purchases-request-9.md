
# Purchases Request 9

*This model accepts additional fields of type unknown.*

## Structure

`PurchasesRequest9`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client65`](../../doc/models/client-65.md) | Required | - |
| `purchase` | [`Purchase`](../../doc/models/purchase.md) | Required | - |
| `paymentMethod` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `sendReceipt` | `string` | Required | - |
| `skipCapture` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PurchasesRequest9 } from 'ps-apimatic-sdk';

const purchasesRequest9: PurchasesRequest9 = {
  client: {
    email: 'example22@paysecure.net',
    country: 'IN',
    city: '123',
    stateCode: 'ca',
    streetAddress: 'test test',
    zipCode: '234567',
    phone: '9999999999',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    currency: 'AUD',
    products: [
      {
        name: 'dk',
        price: '1',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  paymentMethod: 'NEOSURF',
  brandId: '{{your_brand_id_}}',
  sendReceipt: '',
  skipCapture: '',
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

