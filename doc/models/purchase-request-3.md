
# Purchase Request 3

*This model accepts additional fields of type unknown.*

## Structure

`PurchaseRequest3`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client65`](../../doc/models/client-65.md) | Required | - |
| `purchase` | [`Purchase`](../../doc/models/purchase.md) | Required | - |
| `brandId` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PurchaseRequest3 } from 'ps-apimatic-sdk';

const purchaseRequest3: PurchaseRequest3 = {
  client: {
    email: 'customer@example.com',
    country: 'IN',
    city: 'Jaipur',
    stateCode: 'RJ',
    streetAddress: '123 Main Street',
    zipCode: '302001',
    phone: '9999999999',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'Product Name',
        price: '10.00',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  brandId: '{{BrandId}}',
  successRedirect: 'https://yoursite.com/success',
  failureRedirect: 'https://yoursite.com/failure',
  pendingRedirect: 'https://yoursite.com/pending',
  successCallback: 'https://yoursite.com/webhook/success',
  failureCallback: 'https://yoursite.com/webhook/failure',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

