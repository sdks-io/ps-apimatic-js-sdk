
# Purchases Request 4

*This model accepts additional fields of type unknown.*

## Structure

`PurchasesRequest4`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`MClient`](../../doc/models/m-client.md) | Required | - |
| `purchase` | [`Purchase10`](../../doc/models/purchase-10.md) | Required | - |
| `paymentMethod` | `string` | Required | - |
| `merchantRef` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PurchasesRequest4 } from 'ps-apimatic-sdk';

const purchasesRequest4: PurchasesRequest4 = {
  client: {
    email: 'test@gmail.com',
    streetAddress: 'Praça da Bíblia 1308',
    city: 'Jaipur',
    fullName: 'test test',
    zipCode: '302022',
    country: 'IN',
    dateOfBirth: '1994-31-04',
    stateCode: 'RJ',
    phone: '+91 9634988765',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    currency: 'INR',
    products: [
      {
        name: 'test',
        price: 100,
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  paymentMethod: 'UPI-QR',
  merchantRef: 'test12',
  brandId: '{{merchant_brand_id}}',
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

