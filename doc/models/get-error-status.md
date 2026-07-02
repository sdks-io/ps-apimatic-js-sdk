
# Get Error Status

*This model accepts additional fields of type unknown.*

## Structure

`GetErrorStatus`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `code` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { GetErrorStatus } from 'ps-apimatic-sdk';

const getErrorStatus: GetErrorStatus = {
  message: 'Error Message',
  code: 'error_code',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

