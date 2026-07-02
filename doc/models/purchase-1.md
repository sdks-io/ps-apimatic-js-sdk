
# Purchase 1

*This model accepts additional fields of type unknown.*

## Structure

`Purchase1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currency` | `string` | Required | - |
| `products` | [`Product1[]`](../../doc/models/product-1.md) | Required | - |
| `total` | `number` | Required | - |
| `requestAmount` | `number` | Required | - |
| `language` | `string` | Required | - |
| `notes` | `string` | Required | - |
| `debt` | `number` | Required | - |
| `totalFormatted` | `number` | Required | - |
| `taxAmount` | `number` | Required | - |
| `taxPercent` | `number` | Required | - |
| `requestClientDetails` | `string[]` | Required | - |
| `emailMessage` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Purchase1 } from 'ps-apimatic-sdk';

const purchase1: Purchase1 = {
  currency: 'USD',
  products: [
    {
      name: 'product name',
      quantity: 1,
      price: 10,
      discount: 0,
      taxPercent: '0.00',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  total: 10,
  requestAmount: 10,
  language: 'en',
  notes: '',
  debt: 0,
  totalFormatted: 1,
  taxAmount: 0,
  taxPercent: 0,
  requestClientDetails: [],
  emailMessage: '',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

