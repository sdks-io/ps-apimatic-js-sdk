
# Product 17

*This model accepts additional fields of type unknown.*

## Structure

`Product17`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `price` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Product17 } from 'ps-apimatic-sdk';

const product17: Product17 = {
  price: 10,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

