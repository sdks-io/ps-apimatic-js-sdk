
# Create Pay Out Request 4

*This model accepts additional fields of type unknown.*

## Structure

`CreatePayOutRequest4`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client37`](../../doc/models/client-37.md) | Required | - |
| `purpose` | `string` | Required | - |
| `currency` | `string` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreatePayOutRequest4 } from 'ps-apimatic-sdk';

const createPayOutRequest4: CreatePayOutRequest4 = {
  client: {
    email: 'test@gmail.com',
    country: 'EG',
    phone: '9586445444',
    fullName: 'Test Person-uk',
    documentId: '29206260104051',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purpose: 'test payout',
  currency: 'EGP',
  payoutMethod: 'Payout-fawrypay',
  amount: 20,
  successCallback: 'https://success.com',
  failureCallback: 'https://failure.com',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

