
# Client 17

*This model accepts additional fields of type unknown.*

## Structure

`Client17`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `string` | Required | - |
| `country` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client17 } from 'ps-apimatic-sdk';

const client17: Client17 = {
  email: 'ashishm.21190@gmail.com',
  country: 'CA',
  phone: '+14377717874',
  fullName: 'Ashish Mistry',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

