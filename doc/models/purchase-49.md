
# Purchase 49

*This model accepts additional fields of type unknown.*

## Structure

`Purchase49`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currency` | `string` | Required | - |
| `products` | [`Product49[]`](../../doc/models/product-49.md) | Required | - |
| `total` | `number` | Required | - |
| `language` | `string` | Required | - |
| `notes` | `string` | Required | - |
| `debt` | `number` | Required | - |
| `totalFormatted` | `number` | Required | - |
| `taxAmount` | `number` | Required | - |
| `taxPercent` | `number` | Required | - |
| `requestClientDetails` | `string[]` | Required | - |
| `timezone` | `string` | Required | - |
| `emailMessage` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Purchase49 } from 'ps-apimatic-sdk';

const purchase49: Purchase49 = {
  currency: 'USD',
  products: [
    {
      name: 'product name',
      quantity: 1,
      price: 5.86,
      discount: 0,
      taxPercent: '0.00',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  total: 5.86,
  language: 'en',
  notes: '',
  debt: 0,
  totalFormatted: 1,
  taxAmount: 0,
  taxPercent: 0,
  requestClientDetails: [],
  timezone: 'Asia/Hong_Kong',
  emailMessage: '',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

