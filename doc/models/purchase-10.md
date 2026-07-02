
# Purchase 10

*This model accepts additional fields of type unknown.*

## Structure

`Purchase10`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currency` | `string` | Required | - |
| `products` | [`Product7[]`](../../doc/models/product-7.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Purchase10 } from 'ps-apimatic-sdk';

const purchase10: Purchase10 = {
  currency: 'CAD',
  products: [
    {
      name: 'test ',
      price: 1,
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

