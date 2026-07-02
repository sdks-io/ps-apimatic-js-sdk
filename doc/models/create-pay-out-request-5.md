
# Create Pay Out Request 5

*This model accepts additional fields of type unknown.*

## Structure

`CreatePayOutRequest5`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client13`](../../doc/models/client-13.md) | Required | - |
| `payoutMethod` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `currency` | `string` | Required | - |
| `purpose` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `extraParam` | [`ExtraParam13`](../../doc/models/extra-param-13.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreatePayOutRequest5 } from 'ps-apimatic-sdk';

const createPayOutRequest5: CreatePayOutRequest5 = {
  client: {
    customerId: '684fe5700eb6476b179037aa',
    email: 'customer141@email.uk',
    phone: '1234567890',
    fullName: 'Test Person-uk',
    country: 'SG',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  payoutMethod: 'Payout-virtual-cards',
  amount: 10,
  currency: 'USD',
  purpose: 'payout to test',
  successCallback: 'https://success.com',
  failureCallback: 'https://failure.com',
  extraParam: {
    productType: 'WELFARE',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

