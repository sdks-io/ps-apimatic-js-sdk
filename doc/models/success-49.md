
# Success 49

*This model accepts additional fields of type unknown.*

## Structure

`Success49`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success49 } from 'ps-apimatic-sdk';

const success49: Success49 = {
  message: 'Token deleted successfully',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

