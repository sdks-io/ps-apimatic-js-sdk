
# Client 7

*This model accepts additional fields of type unknown.*

## Structure

`Client7`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `string` | Required | - |
| `country` | `string` | Required | - |
| `city` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `streetAddress` | `string` | Required | - |
| `zipCode` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `gender` | `string` | Required | - |
| `dateOfBirth` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client7 } from 'ps-apimatic-sdk';

const client7: Client7 = {
  email: 'rahul@gmail.com',
  country: 'GB',
  city: 'London',
  stateCode: 'QLD',
  fullName: 'Rahul Jain',
  streetAddress: '10 New Burlington Street Apt. 214',
  zipCode: 'W1S 3BE',
  phone: '+44 9876543210',
  gender: 'M',
  dateOfBirth: '1970-07-10',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

