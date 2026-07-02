
# Transaction Data 7

*This model accepts additional fields of type unknown.*

## Structure

`TransactionData7`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentMethod` | `string` | Required | - |
| `flow` | `string` | Required | - |
| `extra` | [`Extra10`](../../doc/models/extra-10.md) | Required | - |
| `country` | `string` | Required | - |
| `attempts` | [`Attempt5[]`](../../doc/models/attempt-5.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { TransactionData7 } from 'ps-apimatic-sdk';

const transactionData7: TransactionData7 = {
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
      clientIp: '103.59.75.42, 172.71.186.102, 130.176.183.14',
      type: 'execute',
      paymentMethod: 'INTERAC-ETRANSFER',
      flow: 'payform',
      successful: true,
      country: 'INTERAC',
      processingTime: 1737549663,
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

