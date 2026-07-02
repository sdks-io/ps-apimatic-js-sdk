
# Purchase 17

*This model accepts additional fields of type unknown.*

## Structure

`Purchase17`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currency` | `string` | Required | - |
| `products` | [`Product17[]`](../../doc/models/product-17.md) | Required | - |
| `total` | `number` | Required | - |
| `language` | `string` | Required | - |
| `totalFormatted` | `number` | Required | - |
| `timezone` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Purchase17 } from 'ps-apimatic-sdk';

const purchase17: Purchase17 = {
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

