
# Purchase Request 2

*This model accepts additional fields of type unknown.*

## Structure

`PurchaseRequest2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client7`](../../doc/models/client-7.md) | Required | - |
| `purchase` | [`Purchase55`](../../doc/models/purchase-55.md) | Required | - |
| `paymentMethod` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `merchantRef` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PurchaseRequest2 } from 'ps-apimatic-sdk';

const purchaseRequest2: PurchaseRequest2 = {
  client: {
    email: 'alpha7.bravo@bravapay.com',
    country: 'GB',
    city: 'London',
    stateCode: 'LND',
    fullName: 'shiba sharma',
    streetAddress: '10 New Burlington StreetApt. 214',
    zipCode: 'SW1A0AA',
    phone: '+447755564318',
    gender: 'male',
    dateOfBirth: '2004-04-31',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    currency: 'GBP',
    products: [
      {
        name: 'e-commerce',
        price: '10',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      {
        name: 'retail',
        price: '11',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    total: 21,
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  paymentMethod: 'OPEN-BANKING',
  brandId: '{{Your.brandID}}',
  merchantRef: '<your_transactionId>',
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

