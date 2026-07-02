
# Checking Balance Partial Success

*This model accepts additional fields of type unknown.*

## Structure

`CheckingBalancePartialSuccess`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentMethod` | `string` | Required | - |
| `status` | `string` | Required | - |
| `gateways` | [`Gateway1[]`](../../doc/models/gateway-1.md) | Required | - |
| `aggregatedBalances` | [`AggregatedBalance[]`](../../doc/models/aggregated-balance.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CheckingBalancePartialSuccess } from 'ps-apimatic-sdk';

const checkingBalancePartialSuccess: CheckingBalancePartialSuccess = {
  paymentMethod: 'paymentMethod4',
  status: 'status8',
  gateways: [
    {
      gatewayName: 'a55Mandate',
      status: 'failed',
      error: {
        code: 'error',
        message: 'Bank does not provide balance',
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
  aggregatedBalances: [
    {
      currency: 'CAD',
      balance: 1616.76,
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

