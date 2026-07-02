
# Purchase 52

*This model accepts additional fields of type unknown.*

## Structure

`Purchase52`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `products` | [`Product[]`](../../doc/models/product.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Purchase52 } from 'ps-apimatic-sdk';

const purchase52: Purchase52 = {
  products: [
    {
      name: 'Apple',
      price: '10',
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

