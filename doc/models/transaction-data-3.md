
# Transaction Data 3

*This model accepts additional fields of type unknown.*

## Structure

`TransactionData3`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentMethod` | `string` | Required | - |
| `flow` | `string` | Required | - |
| `extra` | [`Extra`](../../doc/models/extra.md) | Required | - |
| `country` | `string` | Required | - |
| `attempts` | [`Attempt2[]`](../../doc/models/attempt-2.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { TransactionData3 } from 'ps-apimatic-sdk';

const transactionData3: TransactionData3 = {
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
      successful: true,
      processingTime: 1690295205,
      extra: {
        amount: 9,
        expiryMonth: '10',
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
      paymentMethod: 'VISA',
      flow: 'payform',
      country: 'US',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      clientIp: '149.86.53.48',
      type: 'refund',
      successful: true,
      processingTime: 1690302819,
      extra: {
        amount: 9,
        expiryMonth: 'expiry_month6',
        cardIssuer: 'card_issuer2',
        maskedPan: 'masked_pan8',
        cardBrand: 'card_brand0',
        cardIssuerCountry: 'card_issuer_country4',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      paymentMethod: 'payment_method6',
      flow: 'flow8',
      country: 'country0',
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

