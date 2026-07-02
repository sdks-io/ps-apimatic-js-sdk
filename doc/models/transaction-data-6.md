
# Transaction Data 6

*This model accepts additional fields of type unknown.*

## Structure

`TransactionData6`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentMethod` | `string` | Required | - |
| `flow` | `string` | Required | - |
| `extra` | [`Extra8`](../../doc/models/extra-8.md) | Required | - |
| `country` | `string` | Required | - |
| `attempts` | [`Attempt4[]`](../../doc/models/attempt-4.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { TransactionData6 } from 'ps-apimatic-sdk';

const transactionData6: TransactionData6 = {
  paymentMethod: '',
  flow: 'payform',
  extra: {
    amount: 1,
    maskedPan: 'INTERAC-ETRANSFER',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  country: '',
  attempts: [
    {
      clientIp: '103.59.75.41, 162.158.88.44, 130.176.93.146',
      type: 'execute',
      paymentMethod: 'INTERAC-ETRANSFER',
      flow: 'payform',
      successful: true,
      country: 'INTERAC-ETRANSFER',
      processingTime: 1743769855,
      extra: {
        amount: 1,
        maskedPan: 'INTERAC-ETRANSFER',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
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

