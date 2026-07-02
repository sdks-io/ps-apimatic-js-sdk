
# Create Pay Out Request 1

*This model accepts additional fields of type unknown.*

## Structure

`CreatePayOutRequest1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client17`](../../doc/models/client-17.md) | Required | - |
| `purpose` | `string` | Required | - |
| `currency` | `string` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreatePayOutRequest1 } from 'ps-apimatic-sdk';

const createPayOutRequest1: CreatePayOutRequest1 = {
  client: {
    email: 'ashishm.21190@gmail.com',
    country: 'CA',
    phone: '+14377717874',
    fullName: 'Ashish Mistry',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purpose: 'Transfer Reversed',
  currency: 'CAD',
  payoutMethod: 'PAYOUT-INTERAC-REQUEST-MONEY',
  amount: 1,
  successCallback: 'https://webhook.site/d7660184-d724-480c-bad0-cf0480f5518e',
  failureCallback: 'https://webhook.site/d7660184-d724-480c-bad0-cf0480f5518e',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

