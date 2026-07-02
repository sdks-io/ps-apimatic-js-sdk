
# Client 52

*This model accepts additional fields of type unknown.*

## Structure

`Client52`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Required | - |
| `email` | `string` | Required | - |
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
import { Client52 } from 'ps-apimatic-sdk';

const client52: Client52 = {
  customerId: 'NA',
  email: 'himanshu1@paysecure.net',
  fullName: 'OpHM',
  dateOfBirth: '1800-01-01',
  streetAddress: 'SB-124',
  country: 'BR',
  city: 'DLJPR',
  zipCode: '110001',
  cc: [],
  bcc: [],
  stateCode: 'DL',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

