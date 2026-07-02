
# Client 29

*This model accepts additional fields of type unknown.*

## Structure

`Client29`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `country` | `string` | Required | - |
| `city` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `streetAddress` | `string` | Required | - |
| `zipCode` | `string` | Required | - |
| `dateOfBirth` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `documentId` | `string` | Required | - |
| `documentType` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client29 } from 'ps-apimatic-sdk';

const client29: Client29 = {
  email: 'test@gmail.com',
  fullName: 'test test',
  country: 'BR',
  city: 'Brasília',
  stateCode: 'SP',
  streetAddress: 'Praça da Bíblia 1308',
  zipCode: '57312-140',
  dateOfBirth: '1994-31-04',
  phone: '+558262362732',
  documentId: ' 97c1c590-554b-4449-a0f1-8da9f9756937',
  documentType: 'evp',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

