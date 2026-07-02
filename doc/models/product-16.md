
# Product 16

*This model accepts additional fields of type unknown.*

## Structure

`Product16`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `price` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Product16 } from 'ps-apimatic-sdk';

const product16: Product16 = {
  price: 10,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

