
# Product 49

*This model accepts additional fields of type unknown.*

## Structure

`Product49`

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
import { Product49 } from 'ps-apimatic-sdk';

const product49: Product49 = {
  name: 'product name',
  quantity: 1,
  price: 5.86,
  discount: 0,
  taxPercent: '0.00',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

