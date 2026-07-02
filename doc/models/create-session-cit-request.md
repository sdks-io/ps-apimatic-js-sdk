
# Create Session Cit Request

*This model accepts additional fields of type unknown.*

## Structure

`CreateSessionCitRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Required | - |
| `currency` | `string` | Required | - |
| `products` | [`Product[]`](../../doc/models/product.md) | Required | - |
| `totalAmount` | `string` | Required | - |
| `paymentMethod` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `paymentType` | `string` | Required | - |
| `mandate` | [`Mandate`](../../doc/models/mandate.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreateSessionCitRequest } from 'ps-apimatic-sdk';

const createSessionCitRequest: CreateSessionCitRequest = {
  customerId: '685f870cf3435a2d5b35ee08',
  currency: 'EUR',
  products: [
    {
      name: 'Product1',
      price: '10',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      name: 'Product2',
      price: '10',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  totalAmount: '21',
  paymentMethod: 'VISA',
  successRedirect: 'https://merchant.com/success',
  pendingRedirect: 'https://merchant.com/pending',
  failureRedirect: 'https://merchant.com/failure',
  successCallback: 'https://merchant.com/webhook/success',
  failureCallback: 'https://merchant.com/webhook/failure',
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
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

