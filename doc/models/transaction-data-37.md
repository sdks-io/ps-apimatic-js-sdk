
# Transaction Data 37

*This model accepts additional fields of type unknown.*

## Structure

`TransactionData37`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentMethod` | `string` | Required | - |
| `flow` | `string` | Required | - |
| `extra` | [`Extra52`](../../doc/models/extra-52.md) | Required | - |
| `country` | `string` | Required | - |
| `attempts` | [`Attempt26[]`](../../doc/models/attempt-26.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { TransactionData37 } from 'ps-apimatic-sdk';

const transactionData37: TransactionData37 = {
  paymentMethod: '',
  flow: 'payform',
  extra: {
    expiryMonth: '07',
    amount: 22,
    cardIssuer: 'CIAGROUP',
    maskedPan: '55555555****4444',
    cardBrand: 'MASTER',
    cardIssuerCountry: 'BR',
    cardType: 'DEBIT',
    cardholderName: 'rahul',
    expiryYear: '30',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  country: '',
  attempts: [
    {
      clientIp: '183.83.53.214',
      type: 'execute',
      paymentMethod: 'MASTER',
      flow: 'payform',
      successful: false,
      country: 'BR',
      processingTime: 1766909179,
      extra: {
        expiryMonth: '07',
        amount: 22,
        cardIssuer: 'CIAGROUP',
        maskedPan: '55555555****4444',
        cardBrand: 'MASTER',
        cardIssuerCountry: 'BR',
        cardType: 'DEBIT',
        cardholderName: 'rahul',
        expiryYear: '30',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      error: {
        message: 'This customer can not be processed !',
        code: 'no_mid_found',
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

