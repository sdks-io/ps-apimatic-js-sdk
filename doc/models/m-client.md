
# M Client

*This model accepts additional fields of type unknown.*

## Structure

`MClient`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `string` | Required | - |
| `streetAddress` | `string` | Required | - |
| `city` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `zipCode` | `string` | Required | - |
| `country` | `string` | Required | - |
| `dateOfBirth` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { MClient } from 'ps-apimatic-sdk';

const client: MClient = {
  email: 'rahultest@gmail.com',
  streetAddress: 'Praça João da Silva Machado, 909',
  city: 'Jaipur',
  fullName: 'Rahul Agarwal',
  zipCode: '01000-000',
  country: 'IN',
  dateOfBirth: '1991-07-10',
  stateCode: 'SP',
  phone: '+91 9634458881',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

