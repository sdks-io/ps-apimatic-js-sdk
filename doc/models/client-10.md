
# Client 10

*This model accepts additional fields of type unknown.*

## Structure

`Client10`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Required | - |
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
| `gender` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client10 } from 'ps-apimatic-sdk';

const client10: Client10 = {
  customerId: 'NA',
  email: 'ashishm.21190@gmail.com',
  phone: '+14377717874',
  fullName: 'Test test',
  dateOfBirth: '1970-07-10',
  streetAddress: '10 New Burlington Street Apt. 214',
  country: 'CA',
  city: 'London',
  zipCode: 'W1S 3BE',
  cc: [],
  bcc: [],
  gender: 'MALE',
  stateCode: 'QLD',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

