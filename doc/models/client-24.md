
# Client 24

*This model accepts additional fields of type unknown.*

## Structure

`Client24`

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
| `taxNumber` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client24 } from 'ps-apimatic-sdk';

const client24: Client24 = {
  email: 'test@gmail.com',
  fullName: 'test test',
  country: 'BR',
  city: 'Brasília',
  stateCode: 'SP',
  streetAddress: 'Praça da Bíblia 1308',
  zipCode: '57312-140',
  dateOfBirth: '1994-31-04',
  phone: '+558262362732',
  taxNumber: '39933551809',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

