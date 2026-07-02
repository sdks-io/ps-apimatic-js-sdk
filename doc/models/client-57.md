
# Client 57

*This model accepts additional fields of type unknown.*

## Structure

`Client57`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client57 } from 'ps-apimatic-sdk';

const client57: Client57 = {
  email: 'customer@example.com',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

