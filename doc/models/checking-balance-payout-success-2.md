
# Checking Balance Payout Success 2

*This model accepts additional fields of type unknown.*

## Structure

`CheckingBalancePayoutSuccess2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentMethod` | `string` | Required | - |
| `status` | `string` | Required | - |
| `gateways` | [`Gateway[]`](../../doc/models/gateway.md) | Required | - |
| `aggregatedBalances` | [`AggregatedBalance[]`](../../doc/models/aggregated-balance.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CheckingBalancePayoutSuccess2 } from 'ps-apimatic-sdk';

const checkingBalancePayoutSuccess2: CheckingBalancePayoutSuccess2 = {
  paymentMethod: 'PAYOUT-INTERAC-ETRANSFER',
  status: 'success',
  gateways: [
    {
      gatewayName: 'payhost',
      status: 'success',
      error: 'error8',
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
    },
    {
      gatewayName: 'choicepaypg',
      status: 'success',
      error: 'error8',
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
          balance: 808.38,
          additionalProperties: {
            'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
          },
        }
      ],
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
    },
    {
      currency: 'USD',
      balance: 1611.76,
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

