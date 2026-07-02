
# Client 4

*This model accepts additional fields of type unknown.*

## Structure

`Client4`

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
| `stateCode` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client4 } from 'ps-apimatic-sdk';

const client4: Client4 = {
  customerId: 'NA',
  email: 'divya@paysecure.net',
  phone: '6393000899',
  fullName: 'Test',
  dateOfBirth: '07/01/2000',
  streetAddress: 'test test',
  country: 'IN',
  city: '123',
  zipCode: '234567',
  cc: [],
  bcc: [],
  stateCode: 'ca',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

