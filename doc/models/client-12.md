
# Client 12

*This model accepts additional fields of type unknown.*

## Structure

`Client12`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `type` | `string` | Required | - |
| `customerId` | `string` | Required | - |
| `email` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `dateOfBirth` | `string \| null` | Required | - |
| `streetAddress` | `string` | Required | - |
| `country` | `string` | Required | - |
| `city` | `string` | Required | - |
| `zipCode` | `string` | Required | - |
| `documentId` | `string \| null` | Required | - |
| `documentType` | `string \| null` | Required | - |
| `speiClabe` | `string \| null` | Required | - |
| `speiDebitCard` | `string \| null` | Required | - |
| `speiMobileNo` | `string \| null` | Required | - |
| `stateCode` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client12 } from 'ps-apimatic-sdk';

const client12: Client12 = {
  type: 'PClientDetails',
  customerId: 'NA',
  email: 'gouridausa+2@gmail.com',
  phone: '+14378817874',
  fullName: 'Ashish Mistry',
  dateOfBirth: 'date_of_birth2',
  streetAddress: 'test test',
  country: 'CA',
  city: 'Torronto',
  zipCode: '234567',
  documentId: 'documentId4',
  documentType: 'documentType6',
  speiClabe: 'spei_clabe8',
  speiDebitCard: 'spei_debitCard0',
  speiMobileNo: 'spei_mobileNo6',
  stateCode: 'CT',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

