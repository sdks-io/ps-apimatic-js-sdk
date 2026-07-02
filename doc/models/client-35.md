
# Client 35

*This model accepts additional fields of type unknown.*

## Structure

`Client35`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `dateOfBirth` | `string` | Required | - |
| `streetAddress` | `string` | Required | - |
| `country` | `string` | Required | - |
| `city` | `string` | Required | - |
| `zipCode` | `string` | Required | - |
| `cc` | `string[]` | Required | - |
| `bcc` | `string[]` | Required | - |
| `stateCode` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client35 } from 'ps-apimatic-sdk';

const client35: Client35 = {
  email: 'deepakdeepaksinghal@gmail.com',
  phone: '+447755564318',
  fullName: 'Test test',
  dateOfBirth: '1970-07-10',
  streetAddress: '10 New Burlington Street Apt. 214',
  country: 'EG',
  city: 'London',
  zipCode: 'W1S 3BE',
  cc: [],
  bcc: [],
  stateCode: 'QLD',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

