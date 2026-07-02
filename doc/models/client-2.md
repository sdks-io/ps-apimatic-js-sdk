
# Client 2

*This model accepts additional fields of type unknown.*

## Structure

`Client2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bankAccount` | `string` | Required | - |
| `bankCode` | `string` | Required | - |
| `email` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `dateOfBirth` | `string` | Required | - |
| `personalCode` | `string` | Required | - |
| `streetAddress` | `string` | Required | - |
| `country` | `string` | Required | - |
| `city` | `string` | Required | - |
| `zipCode` | `string` | Required | - |
| `shippingStreetAddress` | `string` | Required | - |
| `shippingCountry` | `string` | Required | - |
| `shippingCity` | `string` | Required | - |
| `shippingZipCode` | `string` | Required | - |
| `cc` | `string[]` | Required | - |
| `bcc` | `string[]` | Required | - |
| `legalName` | `string` | Required | - |
| `brandName` | `string` | Required | - |
| `registrationNumber` | `string` | Required | - |
| `taxNumber` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client2 } from 'ps-apimatic-sdk';

const client2: Client2 = {
  bankAccount: '',
  bankCode: '',
  email: 'example@paysecure.net',
  phone: '',
  fullName: '',
  dateOfBirth: '',
  personalCode: '',
  streetAddress: 'test test',
  country: 'IN',
  city: '123',
  zipCode: '234567',
  shippingStreetAddress: '',
  shippingCountry: '',
  shippingCity: '',
  shippingZipCode: '',
  cc: [],
  bcc: [],
  legalName: '',
  brandName: '',
  registrationNumber: '',
  taxNumber: '',
  stateCode: 'ca',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

