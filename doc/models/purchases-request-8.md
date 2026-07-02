
# Purchases Request 8

*This model accepts additional fields of type unknown.*

## Structure

`PurchasesRequest8`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client8`](../../doc/models/client-8.md) | Required | - |
| `purchase` | [`Purchase7`](../../doc/models/purchase-7.md) | Required | - |
| `extraParam` | [`ExtraParam6`](../../doc/models/extra-param-6.md) | Required | - |
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
import { PurchasesRequest8 } from 'ps-apimatic-sdk';

const purchasesRequest8: PurchasesRequest8 = {
  client: {
    email: 'seo2009@test.com',
    streetAddress: '10 New Burlington Street Apt. 214',
    city: 'London',
    fullName: 'Test test',
    zipCode: 'W1S 3BE',
    country: 'CA',
    stateCode: 'QLD',
    phone: '+447755564318',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    currency: 'CAD',
    expireInMin: '80',
    products: [
      {
        name: 'test ',
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
  extraParam: {
    isCryptoPurchase: 'yes',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  paymentMethod: '',
  brandId: 'f6aff7d7-bb40-4857-bc84-9b4c8310b043',
  successRedirect: 'https://your.redirect.url/getResponse.jsp?success=true',
  pendingRedirect: 'https://your.redirect.url/getResponse.jsp?success=true',
  failureRedirect: 'https://your.redirect.url/getResponse.jsp?success=false',
  successCallback: 'https://your.success.callback.url',
  failureCallback: 'https://your.success.failure.url',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

