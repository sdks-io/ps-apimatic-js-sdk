
# Purchases Request 3

*This model accepts additional fields of type unknown.*

## Structure

`PurchasesRequest3`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client8`](../../doc/models/client-8.md) | Required | - |
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
import { PurchasesRequest3 } from 'ps-apimatic-sdk';

const purchasesRequest3: PurchasesRequest3 = {
  client: {
    email: 'DEEPAKDEEPAKSINGHAL@gmail.com',
    streetAddress: '10 New Burlington Street Apt. 214',
    city: 'London',
    fullName: 'Test test',
    zipCode: 'W1S 3BE',
    country: 'EG',
    stateCode: 'QLD',
    phone: '+447755564318',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    currency: 'EGP',
    products: [
      {
        name: 'test ',
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
  paymentMethod: 'FawryPay',
  brandId: '{{brand_id}}',
  successRedirect: 'https://your.success.redirect.com/getResponse.jsp?success=true',
  pendingRedirect: 'https://staging.paysecure.net/getResponse.jsp?success=true',
  failureRedirect: 'https://your.failure.redirect.com/getResponse.jsp?success=false',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

