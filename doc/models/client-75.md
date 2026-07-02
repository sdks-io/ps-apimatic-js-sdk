
# Client 75

*This model accepts additional fields of type unknown.*

## Structure

`Client75`

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
| `taxNumber` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client75 } from 'ps-apimatic-sdk';

const client75: Client75 = {
  customerId: 'NA',
  email: 'gaurav@gmail.com',
  phone: '9999999999',
  fullName: 'Test test',
  dateOfBirth: '1800-01-01',
  streetAddress: 'test test',
  country: 'US',
  city: '123',
  zipCode: '234567',
  cc: [],
  bcc: [],
  taxNumber: '39933551809',
  stateCode: 'NYC',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

