
# Attempt

*This model accepts additional fields of type unknown.*

## Structure

`Attempt`

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
| `extra` | [`Extra`](../../doc/models/extra.md) | Required | - |
| `error` | [`Error`](../../doc/models/error.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Attempt } from 'ps-apimatic-sdk';

const attempt: Attempt = {
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
};
```

