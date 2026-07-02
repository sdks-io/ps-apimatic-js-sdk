
# Create Purchase Request 1

*This model accepts additional fields of type unknown.*

## Structure

`CreatePurchaseRequest1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`MClient`](../../doc/models/m-client.md) | Required | - |
| `purchase` | [`Purchase10`](../../doc/models/purchase-10.md) | Required | - |
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
import { CreatePurchaseRequest1 } from 'ps-apimatic-sdk';

const createPurchaseRequest1: CreatePurchaseRequest1 = {
  client: {
    email: 'seo2009@test.com',
    streetAddress: '10 New Burlington Street Apt. 214',
    city: 'Sydney',
    fullName: 'Test test',
    zipCode: 'W1S 3BE',
    country: 'KR',
    dateOfBirth: '1970-07-10',
    stateCode: 'QLD',
    phone: '+447755564318',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    currency: 'KRW',
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
  paymentMethod: 'VIRTUAL-ACCOUNT',
  brandId: 'f6aff7d7-bb40-4857-bc84-9b4c8310b043',
  successRedirect: 'https://your.success.redirect.url',
  pendingRedirect: 'https://your.pending.redirect.url',
  failureRedirect: 'https://your.failure.redirect.url',
  successCallback: 'https://your.success.callback.url',
  failureCallback: 'https://your.failure.callback.url',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

