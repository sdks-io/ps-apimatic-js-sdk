
# Purchase 21

*This model accepts additional fields of type unknown.*

## Structure

`Purchase21`

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
| `requestClientDetails` | `string[]` | Required | - |
| `timezone` | `string` | Required | - |
| `emailMessage` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Purchase21 } from 'ps-apimatic-sdk';

const purchase21: Purchase21 = {
  currency: 'EGP',
  products: [
    {
      name: 'test',
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
  language: 'en',
  notes: '',
  debt: 0,
  totalFormatted: 1,
  requestClientDetails: [],
  timezone: 'MIT',
  emailMessage: '',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

