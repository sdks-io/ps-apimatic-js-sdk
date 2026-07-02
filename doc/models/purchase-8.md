
# Purchase 8

*This model accepts additional fields of type unknown.*

## Structure

`Purchase8`

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
| `expireInMin` | `string` | Required | - |
| `taxAmount` | `number` | Required | - |
| `taxPercent` | `number` | Required | - |
| `requestClientDetails` | `string[]` | Required | - |
| `emailMessage` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Purchase8 } from 'ps-apimatic-sdk';

const purchase8: Purchase8 = {
  currency: 'CAD',
  products: [
    {
      name: 'test',
      quantity: 1,
      price: 1,
      discount: 0,
      taxPercent: '0.00',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  total: 1,
  language: 'en',
  notes: '',
  debt: 0,
  totalFormatted: 1,
  expireInMin: '43200',
  taxAmount: 0,
  taxPercent: 0,
  requestClientDetails: [],
  emailMessage: '',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

