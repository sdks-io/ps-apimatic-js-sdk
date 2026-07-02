
# Client 104

*This model accepts additional fields of type unknown.*

## Structure

`Client104`

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
| `bankAccountNumber` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client104 } from 'ps-apimatic-sdk';

const client104: Client104 = {
  customerId: 'NA',
  email: 'sl68792.bravo@bravapay.com',
  phone: '0557719399',
  fullName: 'Test user',
  dateOfBirth: '2004-07-12',
  streetAddress: '10 New Burlington StreetApt. 214',
  country: 'CA',
  city: 'London',
  zipCode: 'W1S 3BE',
  cc: [],
  bcc: [],
  taxNumber: '+447755564318',
  bankAccountNumber: '1345789678',
  stateCode: 'QLD',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

