
# Client 66

*This model accepts additional fields of type unknown.*

## Structure

`Client66`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Required | - |
| `email` | `string` | Required | - |
| `phone` | `string` | Required | - |
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
import { Client66 } from 'ps-apimatic-sdk';

const client66: Client66 = {
  customerId: 'NA',
  email: 'example22@paysecure.net',
  phone: '9999999999',
  dateOfBirth: '1800-01-01',
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

