
# Purchase 16

*This model accepts additional fields of type unknown.*

## Structure

`Purchase16`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currency` | `string` | Required | - |
| `products` | [`Product16[]`](../../doc/models/product-16.md) | Required | - |
| `total` | `number` | Required | - |
| `language` | `string` | Required | - |
| `totalFormatted` | `number` | Required | - |
| `timezone` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Purchase16 } from 'ps-apimatic-sdk';

const purchase16: Purchase16 = {
  currency: 'USD',
  products: [
    {
      price: 10,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  total: 10,
  language: 'en',
  totalFormatted: 1,
  timezone: 'MIT',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

