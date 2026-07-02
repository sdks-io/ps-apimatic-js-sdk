
# Client 86

*This model accepts additional fields of type unknown.*

## Structure

`Client86`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `streetAddress` | `string` | Required | - |
| `country` | `string` | Required | - |
| `city` | `string` | Required | - |
| `zipCode` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client86 } from 'ps-apimatic-sdk';

const client86: Client86 = {
  email: 'customer141@email.uk',
  fullName: 'Test Person-uk',
  streetAddress: 'Random city address',
  country: 'SG',
  city: 'Singapore',
  zipCode: '123456',
  stateCode: 'test',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

