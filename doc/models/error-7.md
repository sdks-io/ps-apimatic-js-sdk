
# Error 7

*This model accepts additional fields of type unknown.*

## Structure

`Error7`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `code` | `string \| undefined` | Optional | - |
| `message` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Error7 } from 'ps-apimatic-sdk';

const error7: Error7 = {
  code: 'error',
  message: 'Bank does not provide balance',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

