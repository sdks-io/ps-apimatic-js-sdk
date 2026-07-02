
# Attempt 26

*This model accepts additional fields of type unknown.*

## Structure

`Attempt26`

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
| `extra` | [`Extra52`](../../doc/models/extra-52.md) | Required | - |
| `error` | [`Error`](../../doc/models/error.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Attempt26 } from 'ps-apimatic-sdk';

const attempt26: Attempt26 = {
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
};
```

