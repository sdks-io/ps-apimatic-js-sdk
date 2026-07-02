
# Checking Balance Payout Error 2

*This model accepts additional fields of type unknown.*

## Structure

`CheckingBalancePayoutError2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentMethod` | `string` | Required | - |
| `status` | `string` | Required | - |
| `gateways` | [`Gateway2[]`](../../doc/models/gateway-2.md) | Required | - |
| `aggregatedBalances` | `string[]` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CheckingBalancePayoutError2 } from 'ps-apimatic-sdk';

const checkingBalancePayoutError2: CheckingBalancePayoutError2 = {
  paymentMethod: 'PAYOUT-INTERAC',
  status: 'failed',
  gateways: [
    {
      gatewayName: 'payhost',
      status: 'failed',
      error: {
        message: 'Bank does not provide balance',
        code: 'error',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      balances: [],
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  aggregatedBalances: [],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

