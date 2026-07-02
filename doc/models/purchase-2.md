
# Purchase 2

*This model accepts additional fields of type unknown.*

## Structure

`Purchase2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currency` | `string` | Required | - |
| `products` | [`Product2[]`](../../doc/models/product-2.md) | Required | - |
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
import { Purchase2 } from 'ps-apimatic-sdk';

const purchase2: Purchase2 = {
  currency: 'USD',
  products: [
    {
      name: 'dk',
      quantity: 1,
      price: 100,
      discount: 0,
      taxPercent: '0.00',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  total: 100,
  language: 'en',
  notes: '',
  debt: 0,
  totalFormatted: 1,
  requestClientDetails: [],
  timezone: 'America/Edmonton',
  emailMessage: '',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

