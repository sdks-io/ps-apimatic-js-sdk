
# Create Purchase Mit Request

*This model accepts additional fields of type unknown.*

## Structure

`CreatePurchaseMitRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client80`](../../doc/models/client-80.md) | Required | - |
| `purchase` | [`Purchase10`](../../doc/models/purchase-10.md) | Required | - |
| `merchantRef` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `paymentType` | `string` | Required | - |
| `mandateId` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreatePurchaseMitRequest } from 'ps-apimatic-sdk';

const createPurchaseMitRequest: CreatePurchaseMitRequest = {
  client: {
    customerId: '685f870cf3435a2d5b35ee08',
    email: 'abby.aadeniran@gmail.com',
    phone: '+44 07932665877',
    fullName: 'Navya Jain',
    streetAddress: 'Flat 61 Priory Court Romford RM7 0FY',
    country: 'GB',
    city: 'London',
    zipCode: '234567',
    stateCode: 'LO',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'test',
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
  merchantRef: '{{your-merchant-ref}}',
  brandId: '{{merchant_brand_id}}',
  paymentType: 'recurring',
  mandateId: '{{mandate-id}}',
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

