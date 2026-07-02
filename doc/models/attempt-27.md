
# Attempt 27

*This model accepts additional fields of type unknown.*

## Structure

`Attempt27`

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
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Attempt27 } from 'ps-apimatic-sdk';

const attempt27: Attempt27 = {
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
};
```

