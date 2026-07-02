
# Purchase 48

*This model accepts additional fields of type unknown.*

## Structure

`Purchase48`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currency` | `string` | Required | - |
| `products` | [`Product48[]`](../../doc/models/product-48.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Purchase48 } from 'ps-apimatic-sdk';

const purchase48: Purchase48 = {
  currency: 'USD',
  products: [
    {
      name: 'product name',
      price: 5.86,
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

