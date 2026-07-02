
# Create Purchase Request

*This model accepts additional fields of type unknown.*

## Structure

`CreatePurchaseRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client7`](../../doc/models/client-7.md) | Required | - |
| `purchase` | [`Purchase10`](../../doc/models/purchase-10.md) | Required | - |
| `paymentMethod` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreatePurchaseRequest } from 'ps-apimatic-sdk';

const createPurchaseRequest: CreatePurchaseRequest = {
  client: {
    email: 'ashishm.21190@gmail.com',
    country: 'CA',
    city: 'London',
    stateCode: 'QLD',
    fullName: 'Test test',
    streetAddress: '10 New Burlington Street Apt. 214',
    zipCode: 'W1S 3BE',
    phone: '+447755564318',
    gender: 'MALE',
    dateOfBirth: '1970-07-10',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    currency: 'CAD',
    products: [
      {
        name: 'test ',
        price: 1,
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  paymentMethod: 'INTERAC-REQUEST-MONEY',
  brandId: '0cea7af3-23b2-4278-ab94-acf4076cbee4',
  successRedirect: 'https://your.redirect.url/getResponse',
  failureRedirect: 'https://your.redirect.url/getResponse',
  successCallback: 'https://your.success.callback.url',
  failureCallback: 'https://your.success.failure.url',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

