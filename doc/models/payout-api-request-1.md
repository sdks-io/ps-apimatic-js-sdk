
# Payout Api Request 1

*This model accepts additional fields of type unknown.*

## Structure

`PayoutApiRequest1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client67`](../../doc/models/client-67.md) | Required | - |
| `purpose` | `string` | Required | - |
| `currency` | `string` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PayoutApiRequest1 } from 'ps-apimatic-sdk';

const payoutApiRequest1: PayoutApiRequest1 = {
  client: {
    email: 'akshayadeepsinghal@gmail.com',
    country: 'AU',
    phone: '+11111111',
    fullName: 'PAYOUT USER',
    stateCode: 'test',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purpose: 'test payout',
  currency: 'AUD',
  payoutMethod: 'PAYOUT-NEOSURF',
  amount: 1,
  successCallback: 'https://success.com',
  failureCallback: 'https://failure.com',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

