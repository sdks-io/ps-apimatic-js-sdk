
# Client 26

*This model accepts additional fields of type unknown.*

## Structure

`Client26`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `taxNumber` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client26 } from 'ps-apimatic-sdk';

const client26: Client26 = {
  email: 'test@gmail.com',
  fullName: 'Test test',
  taxNumber: '39933551809',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

