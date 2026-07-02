
# Gateway

*This model accepts additional fields of type unknown.*

## Structure

`Gateway`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `gatewayName` | `string` | Required | - |
| `status` | `string` | Required | - |
| `error` | `string \| null` | Required | - |
| `balances` | [`Balance[]`](../../doc/models/balance.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Gateway } from 'ps-apimatic-sdk';

const gateway: Gateway = {
  gatewayName: 'payhost',
  status: 'success',
  error: 'error4',
  balances: [
    {
      currency: 'CAD',
      balance: 808.38,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      currency: 'USD',
      balance: 803.38,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

