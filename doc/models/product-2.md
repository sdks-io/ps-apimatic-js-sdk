
# Product 2

*This model accepts additional fields of type unknown.*

## Structure

`Product2`

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
import { Product2 } from 'ps-apimatic-sdk';

const product2: Product2 = {
  name: 'dk',
  quantity: 1,
  price: 100,
  discount: 0,
  taxPercent: '0.00',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

