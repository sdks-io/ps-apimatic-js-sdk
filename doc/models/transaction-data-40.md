
# Transaction Data 40

*This model accepts additional fields of type unknown.*

## Structure

`TransactionData40`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentMethod` | `string` | Required | - |
| `flow` | `string` | Required | - |
| `extra` | [`Extra52`](../../doc/models/extra-52.md) | Required | - |
| `country` | `string` | Required | - |
| `attempts` | [`Attempt27[]`](../../doc/models/attempt-27.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { TransactionData40 } from 'ps-apimatic-sdk';

const transactionData40: TransactionData40 = {
  paymentMethod: '',
  flow: 'payform',
  extra: {
    expiryMonth: '04',
    amount: 1,
    cardIssuer: 'REVOLUT BANK UAB',
    maskedPan: '41659827****0724',
    cardBrand: 'VISA',
    cardIssuerCountry: 'CH',
    cardType: 'DEBIT',
    cardholderName: 'Amit Hooja',
    expiryYear: '31',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  country: '',
  attempts: [
    {
      clientIp: '183.82.186.156',
      type: 'execute',
      paymentMethod: 'VISA',
      flow: 'payform',
      successful: true,
      country: 'CH',
      processingTime: 1777914887,
      extra: {
        expiryMonth: '04',
        amount: 1,
        cardIssuer: 'REVOLUT BANK UAB',
        maskedPan: '41659827****0724',
        cardBrand: 'VISA',
        cardIssuerCountry: 'CH',
        cardType: 'DEBIT',
        cardholderName: 'Amit Hooja',
        expiryYear: '31',
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

