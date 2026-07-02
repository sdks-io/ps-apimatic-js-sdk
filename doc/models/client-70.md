
# Client 70

*This model accepts additional fields of type unknown.*

## Structure

`Client70`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Required | - |
| `email` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `fullName` | `string` | Required | - |
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
import { Client70 } from 'ps-apimatic-sdk';

const client70: Client70 = {
  customerId: 'NA',
  email: 'arun44@gmail.com',
  phone: '+237679544810',
  fullName: 'Olive Tsafack',
  streetAddress: 'test test',
  country: 'AU',
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

