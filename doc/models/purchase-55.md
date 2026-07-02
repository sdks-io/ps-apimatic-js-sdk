
# Purchase 55

*This model accepts additional fields of type unknown.*

## Structure

`Purchase55`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currency` | `string` | Required | - |
| `products` | [`Product[]`](../../doc/models/product.md) | Required | - |
| `total` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Purchase55 } from 'ps-apimatic-sdk';

const purchase55: Purchase55 = {
  currency: 'GBP',
  products: [
    {
      name: 'e-commerce',
      price: '10',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      name: 'retail',
      price: '11',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  total: 21,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

