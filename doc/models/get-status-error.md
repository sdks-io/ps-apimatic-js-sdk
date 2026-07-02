
# Get Status Error

*This model accepts additional fields of type unknown.*

## Structure

`GetStatusError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `code` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { GetStatusError } from 'ps-apimatic-sdk';

const getStatusError: GetStatusError = {
  message: 'Error Message',
  code: 'error_code',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

