
# Purchase 56

*This model accepts additional fields of type unknown.*

## Structure

`Purchase56`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currency` | `string` | Required | - |
| `products` | [`Product1[]`](../../doc/models/product-1.md) | Required | - |
| `total` | `number` | Required | - |
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
import { Purchase56 } from 'ps-apimatic-sdk';

const purchase56: Purchase56 = {
  currency: 'GBP',
  products: [
    {
      name: 'e-commerce',
      quantity: 1,
      price: 10,
      discount: 0,
      taxPercent: '0.00',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      name: 'retail',
      quantity: 1,
      price: 11,
      discount: 0,
      taxPercent: '0.00',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  total: 21,
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

