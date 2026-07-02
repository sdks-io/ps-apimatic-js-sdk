
# Product 48

*This model accepts additional fields of type unknown.*

## Structure

`Product48`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Required | - |
| `price` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Product48 } from 'ps-apimatic-sdk';

const product48: Product48 = {
  name: 'product name',
  price: 5.86,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

