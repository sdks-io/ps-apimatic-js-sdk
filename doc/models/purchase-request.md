
# Purchase Request

*This model accepts additional fields of type unknown.*

## Structure

`PurchaseRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`MClient`](../../doc/models/m-client.md) | Required | - |
| `purchase` | [`Purchase`](../../doc/models/purchase.md) | Required | - |
| `merchantRef` | `string` | Required | - |
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
import { PurchaseRequest } from 'ps-apimatic-sdk';

const purchaseRequest: PurchaseRequest = {
  client: {
    email: 'rahultest@gmail.com',
    streetAddress: 'Praça João da Silva Machado, 909',
    city: 'Jaipur',
    fullName: 'Rahul Agarwal',
    zipCode: '01000-000',
    country: 'IN',
    dateOfBirth: '1991-07-10',
    stateCode: 'SP',
    phone: '+91 9634458881',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    currency: 'EUR',
    products: [
      {
        name: 'e-commerce',
        price: '5',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  merchantRef: 'rahul2345test',
  paymentMethod: 'MASTER',
  brandId: 'your-brand-id',
  successRedirect: '//your.success.redirect.com',
  pendingRedirect: '//your.pending.redirect.com',
  failureRedirect: '//your.failue.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

