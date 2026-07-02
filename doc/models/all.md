
# All

*This model accepts additional fields of type unknown.*

## Structure

`All`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `code` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { All } from 'ps-apimatic-sdk';

const all: All = {
  message: 'Authorization header missing',
  code: 'authentication_failed',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

