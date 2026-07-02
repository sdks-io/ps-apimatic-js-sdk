
# Create Purchase Request 2

*This model accepts additional fields of type unknown.*

## Structure

`CreatePurchaseRequest2`

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
import { CreatePurchaseRequest2 } from 'ps-apimatic-sdk';

const createPurchaseRequest2: CreatePurchaseRequest2 = {
  client: {
    email: 'test@gmail.com',
    streetAddress: '10 New Burlington Street Apt. 214',
    city: 'Zurich',
    fullName: 'Test test',
    zipCode: 'W1S 3BE',
    country: 'DE',
    dateOfBirth: '1970-07-10',
    stateCode: 'QLD',
    phone: '+447755564318',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    currency: 'EUR',
    products: [
      {
        name: 'product name',
        price: '16',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  merchantRef: 'your-order-id',
  paymentMethod: 'BANKTRANSFER',
  brandId: 'your-brandid',
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

