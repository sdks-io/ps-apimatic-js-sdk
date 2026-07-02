
# Transaction Data 2

*This model accepts additional fields of type unknown.*

## Structure

`TransactionData2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentMethod` | `string` | Required | - |
| `flow` | `string` | Required | - |
| `extra` | [`Extra`](../../doc/models/extra.md) | Required | - |
| `country` | `string` | Required | - |
| `attempts` | [`Attempt1[]`](../../doc/models/attempt-1.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { TransactionData2 } from 'ps-apimatic-sdk';

const transactionData2: TransactionData2 = {
  paymentMethod: '',
  flow: 'payform',
  extra: {
    expiryMonth: '10',
    amount: 9,
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
      successful: true,
      country: 'US',
      processingTime: 1690295205,
      extra: {
        expiryMonth: '10',
        amount: 9,
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

