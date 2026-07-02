
# Purchases Request 6

*This model accepts additional fields of type unknown.*

## Structure

`PurchasesRequest6`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`MClient`](../../doc/models/m-client.md) | Required | - |
| `purchase` | [`Purchase10`](../../doc/models/purchase-10.md) | Required | - |
| `brandId` | `string` | Required | - |
| `paymentMethod` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PurchasesRequest6 } from 'ps-apimatic-sdk';

const purchasesRequest6: PurchasesRequest6 = {
  client: {
    email: 'rahultest@gmail.com',
    streetAddress: '10 New Burlington StreetApt. 214',
    city: 'London',
    fullName: 'Rahul Agarwal',
    zipCode: 'W1S 3BE',
    country: 'GB',
    dateOfBirth: '1994-31-04',
    stateCode: 'RJ',
    phone: '+91 9634088561',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    currency: 'EUR',
    products: [
      {
        name: 'gaming cards ',
        price: 10,
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  brandId: 'your-brandid',
  paymentMethod: 'GOOGLEPAY-REDIRECT',
  successRedirect: 'https://your-redirect-url?issucces=true',
  pendingRedirect: 'https://your-redirect-url?ispending=true',
  failureRedirect: 'https://your-redirect-url?isfailure=true',
  successCallback: 'https://your-webhook-url',
  failureCallback: 'https://your-webhook-url',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

