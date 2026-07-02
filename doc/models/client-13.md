
# Client 13

*This model accepts additional fields of type unknown.*

## Structure

`Client13`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Required | - |
| `email` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `country` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client13 } from 'ps-apimatic-sdk';

const client13: Client13 = {
  customerId: 'NA',
  email: 'ashishm.21190@gmail.com',
  phone: '+14377717874',
  fullName: 'Ashish Mistry',
  country: 'CA',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

