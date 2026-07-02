
# Attempt 28

*This model accepts additional fields of type unknown.*

## Structure

`Attempt28`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `clientIp` | `string` | Required | - |
| `type` | `string` | Required | - |
| `paymentMethod` | `string` | Required | - |
| `flow` | `string` | Required | - |
| `successful` | `boolean` | Required | - |
| `country` | `string` | Required | - |
| `processingTime` | `number` | Required | - |
| `extra` | [`Extra57`](../../doc/models/extra-57.md) | Required | - |
| `error` | [`Error`](../../doc/models/error.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Attempt28 } from 'ps-apimatic-sdk';

const attempt28: Attempt28 = {
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
};
```

