
# Transaction Data 41

*This model accepts additional fields of type unknown.*

## Structure

`TransactionData41`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentMethod` | `string` | Required | - |
| `flow` | `string` | Required | - |
| `extra` | [`Extra52`](../../doc/models/extra-52.md) | Required | - |
| `country` | `string` | Required | - |
| `attempts` | [`Attempt28[]`](../../doc/models/attempt-28.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { TransactionData41 } from 'ps-apimatic-sdk';

const transactionData41: TransactionData41 = {
  paymentMethod: '',
  flow: 'payform',
  extra: {
    expiryMonth: '01',
    amount: 10,
    cardIssuer: 'VISION BANK',
    maskedPan: '42222222*2222',
    cardBrand: 'VISA',
    cardIssuerCountry: 'SA',
    cardType: 'DEBIT',
    cardholderName: 'fgjhknms',
    expiryYear: '29',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  country: '',
  attempts: [
    {
      clientIp: '49.36.232.107',
      type: 'execute',
      paymentMethod: 'VISA',
      flow: 'payform',
      successful: false,
      country: 'VISA',
      processingTime: 1769188612,
      extra: {
        amount: 10,
        maskedPan: 'VISA',
        cardBrand: 'VISA',
        cardIssuerCountry: 'VISA',
        cardholderName: 'Test user',
        expiryMonth: 'expiry_month6',
        cardIssuer: 'card_issuer2',
        cardType: 'card_type8',
        expiryYear: 'expiry_year4',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      error: {
        message: 'This customer can not be processed !',
        code: 'transaction_error',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      clientIp: '',
      type: 'execute',
      paymentMethod: 'VISA',
      flow: 'payform',
      successful: false,
      country: 'SA',
      processingTime: 1769188613,
      extra: {
        amount: 10,
        maskedPan: '42222222*2222',
        cardBrand: 'VISA',
        cardIssuerCountry: 'SA',
        cardholderName: 'fgjhknms',
        expiryMonth: '01',
        cardIssuer: 'VISION BANK',
        cardType: 'DEBIT',
        expiryYear: '29',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      error: {
        message: 'ERROR_PARSING_GROUP_ID',
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

