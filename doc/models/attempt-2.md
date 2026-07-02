
# Attempt 2

*This model accepts additional fields of type unknown.*

## Structure

`Attempt2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `clientIp` | `string` | Required | - |
| `type` | `string` | Required | - |
| `paymentMethod` | `string \| undefined` | Optional | - |
| `flow` | `string \| undefined` | Optional | - |
| `successful` | `boolean` | Required | - |
| `country` | `string \| undefined` | Optional | - |
| `processingTime` | `number` | Required | - |
| `extra` | [`Extra5`](../../doc/models/extra-5.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Attempt2 } from 'ps-apimatic-sdk';

const attempt2: Attempt2 = {
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
};
```

