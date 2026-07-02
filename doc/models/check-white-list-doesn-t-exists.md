
# Check White List Doesn T Exists

*This model accepts additional fields of type unknown.*

## Structure

`CheckWhiteListDoesnTExists`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CheckWhiteListDoesnTExists } from 'ps-apimatic-sdk';

const checkWhiteListDoesnTExists: CheckWhiteListDoesnTExists = {
  message: 'NOTEXIST',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

