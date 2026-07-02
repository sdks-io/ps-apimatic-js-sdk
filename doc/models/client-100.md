
# Client 100

*This model accepts additional fields of type unknown.*

## Structure

`Client100`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Required | - |
| `email` | `string` | Required | - |
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
import { Client100 } from 'ps-apimatic-sdk';

const client100: Client100 = {
  customerId: 'NA',
  email: 'paysecuretest@gmail.com',
  streetAddress: 'Flat 61 Priory Court Romford RM7 0FY',
  country: 'GB',
  city: 'London',
  zipCode: '234567',
  cc: [],
  bcc: [],
  stateCode: 'LO',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

