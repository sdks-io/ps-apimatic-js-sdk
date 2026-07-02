
# New Request Request

*This model accepts additional fields of type unknown.*

## Structure

`NewRequestRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client17`](../../doc/models/client-17.md) | Required | - |
| `purpose` | `string` | Required | - |
| `currency` | `string` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `extraParam` | [`ExtraParam7`](../../doc/models/extra-param-7.md) | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { NewRequestRequest } from 'ps-apimatic-sdk';

const newRequestRequest: NewRequestRequest = {
  client: {
    email: 'ashishm.21190@gmail.com',
    country: 'CA',
    phone: '7665230591',
    fullName: 'Test Person-uk',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purpose: 'testing payout',
  currency: 'AUD',
  payoutMethod: 'PAYOUT-PAYID',
  amount: 50,
  extraParam: {
    payId: 'KeU6r2egQmQZeqUfkPYC7HSU1EDrn2GYyU',
    bankName: 'test bank name',
    accountName: 'arun',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  successCallback: '<https://success.com>',
  failureCallback: '<https://failure.com>',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

