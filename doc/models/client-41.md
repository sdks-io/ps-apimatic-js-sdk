
# Client 41

*This model accepts additional fields of type unknown.*

## Structure

`Client41`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `string` | Required | - |
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
import { Client41 } from 'ps-apimatic-sdk';

const client41: Client41 = {
  email: 'deepakdeepaksinghal@gmail.com',
  dateOfBirth: '1970-07-10',
  streetAddress: '10 New Burlington Street Apt. 214',
  country: 'IN',
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

