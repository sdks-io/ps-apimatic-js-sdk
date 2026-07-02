
# Create Purchase Cit Request

*This model accepts additional fields of type unknown.*

## Structure

`CreatePurchaseCitRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client8`](../../doc/models/client-8.md) | Required | - |
| `purchase` | [`Purchase`](../../doc/models/purchase.md) | Required | - |
| `merchantRef` | `string` | Required | - |
| `paymentMethod` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `paymentType` | `string` | Required | - |
| `mandate` | [`Mandate`](../../doc/models/mandate.md) | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreatePurchaseCitRequest } from 'ps-apimatic-sdk';

const createPurchaseCitRequest: CreatePurchaseCitRequest = {
  client: {
    email: 'rahul@gmail.com',
    streetAddress: 'Flat 61 Priory Court Romford RM7 0FY',
    city: 'London',
    fullName: 'Rahul Agarwal',
    zipCode: '234567',
    country: 'GB',
    stateCode: 'LO',
    phone: '+44 07932665877',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'product name',
        price: '1',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  merchantRef: 'your-merchant-ref',
  paymentMethod: 'MASTER',
  brandId: 'your-brand-id',
  paymentType: 'mandate',
  mandate: {
    mandateMaxAmount: '5000',
    amountVariability: 'Fixed',
    startDate: '1598965200',
    endDate: '1914141600',
    frequency: 'MONTHLY',
    rule: 'on',
    value: 1,
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  successRedirect: 'https://merchant.com/success',
  pendingRedirect: 'https://merchant.com/pending',
  failureRedirect: 'https://merchant.com/failure',
  successCallback: 'https://merchant.com/webhook/success',
  failureCallback: 'https://merchant.com/webhook/failure',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

