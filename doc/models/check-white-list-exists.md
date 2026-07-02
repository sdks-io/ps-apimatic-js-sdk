
# Check White List Exists

*This model accepts additional fields of type unknown.*

## Structure

`CheckWhiteListExists`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CheckWhiteListExists } from 'ps-apimatic-sdk';

const checkWhiteListExists: CheckWhiteListExists = {
  message: 'EXIST',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

