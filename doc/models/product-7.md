
# Product 7

*This model accepts additional fields of type unknown.*

## Structure

`Product7`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Required | - |
| `price` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Product7 } from 'ps-apimatic-sdk';

const product7: Product7 = {
  name: 'test ',
  price: 100,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

