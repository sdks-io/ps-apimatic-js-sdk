
# Product 1

*This model accepts additional fields of type unknown.*

## Structure

`Product1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Required | - |
| `quantity` | `number` | Required | - |
| `price` | `number` | Required | - |
| `discount` | `number` | Required | - |
| `taxPercent` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Product1 } from 'ps-apimatic-sdk';

const product1: Product1 = {
  name: 'product name',
  quantity: 1,
  price: 10,
  discount: 0,
  taxPercent: '0.00',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

