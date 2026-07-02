
# Purchase 7

*This model accepts additional fields of type unknown.*

## Structure

`Purchase7`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currency` | `string` | Required | - |
| `expireInMin` | `string` | Required | - |
| `products` | [`Product7[]`](../../doc/models/product-7.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Purchase7 } from 'ps-apimatic-sdk';

const purchase7: Purchase7 = {
  currency: 'CAD',
  expireInMin: '80',
  products: [
    {
      name: 'test ',
      price: 100,
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

