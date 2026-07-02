
# Purchases Request 5

*This model accepts additional fields of type unknown.*

## Structure

`PurchasesRequest5`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`MClient`](../../doc/models/m-client.md) | Required | - |
| `purchase` | [`Purchase`](../../doc/models/purchase.md) | Required | - |
| `paymentMethod` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PurchasesRequest5 } from 'ps-apimatic-sdk';

const purchasesRequest5: PurchasesRequest5 = {
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
  purchase: {
    currency: 'CDF',
    products: [
      {
        name: 'Test Product',
        price: '100',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  paymentMethod: 'MOBILEMONEY',
  brandId: 'your-brand-id',
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

