
# Client 103

*This model accepts additional fields of type unknown.*

## Structure

`Client103`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Required | - |
| `email` | `string` | Required | - |
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
import { Client103 } from 'ps-apimatic-sdk';

const client103: Client103 = {
  customerId: 'NA',
  email: 'recurring@yopmail.com',
  dateOfBirth: '1800-01-01',
  streetAddress: '120, jaipur',
  country: 'CA',
  city: 'London',
  zipCode: 'W1S 3BE',
  cc: [],
  bcc: [],
  stateCode: 'QLD',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

