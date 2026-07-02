
# Client 67

*This model accepts additional fields of type unknown.*

## Structure

`Client67`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `string` | Required | - |
| `country` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client67 } from 'ps-apimatic-sdk';

const client67: Client67 = {
  email: 'akshayadeepsinghal@gmail.com',
  country: 'AU',
  phone: '+11111111',
  fullName: 'PAYOUT USER',
  stateCode: 'test',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

