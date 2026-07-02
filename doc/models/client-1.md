
# Client 1

*This model accepts additional fields of type unknown.*

## Structure

`Client1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Required | - |
| `email` | `string` | Required | - |
| `phone` | `string` | Required | - |
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
import { Client1 } from 'ps-apimatic-sdk';

const client1: Client1 = {
  customerId: 'NA',
  email: 'rahultest@gmail.com',
  phone: '6393000899',
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

