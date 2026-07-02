
# Client 68

*This model accepts additional fields of type unknown.*

## Structure

`Client68`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Required | - |
| `email` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `country` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client68 } from 'ps-apimatic-sdk';

const client68: Client68 = {
  customerId: 'NA',
  email: 'akshayadeepsinghal@gmail.com',
  phone: '+11111111',
  fullName: 'PAYOUT USER',
  country: 'AU',
  stateCode: 'test',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

