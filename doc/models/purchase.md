
# Purchase

*This model accepts additional fields of type unknown.*

## Structure

`Purchase`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currency` | `string` | Required | - |
| `products` | [`Product[]`](../../doc/models/product.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Purchase } from 'ps-apimatic-sdk';

const purchase: Purchase = {
  currency: 'EUR',
  products: [
    {
      name: 'e-commerce',
      price: '5',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

