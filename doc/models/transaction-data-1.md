
# Transaction Data 1

*This model accepts additional fields of type unknown.*

## Structure

`TransactionData1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentMethod` | `string` | Required | - |
| `flow` | `string` | Required | - |
| `extra` | [`Extra`](../../doc/models/extra.md) | Required | - |
| `country` | `string` | Required | - |
| `attempts` | [`Attempt[]`](../../doc/models/attempt.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { TransactionData1 } from 'ps-apimatic-sdk';

const transactionData1: TransactionData1 = {
  paymentMethod: '',
  flow: 'payform',
  extra: {
    expiryMonth: '10',
    amount: 100,
    cardIssuer: '1-800-432-3117',
    maskedPan: '411111XXXXXX1111',
    cardBrand: 'VISA',
    cardIssuerCountry: 'US',
    cardholderName: 'dk',
    expiryYear: '23',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  country: '',
  attempts: [
    {
      clientIp: '149.86.53.48',
      type: 'execute',
      paymentMethod: 'VISA',
      flow: 'payform',
      successful: false,
      country: 'US',
      processingTime: 1690294279,
      extra: {
        expiryMonth: '10',
        amount: 100,
        cardIssuer: '1-800-432-3117',
        maskedPan: '411111XXXXXX1111',
        cardBrand: 'VISA',
        cardIssuerCountry: 'US',
        cardholderName: 'dk',
        expiryYear: '23',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      error: {
        message: 'Transaction Failed',
        code: 'transaction_error',
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

