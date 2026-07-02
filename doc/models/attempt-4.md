
# Attempt 4

*This model accepts additional fields of type unknown.*

## Structure

`Attempt4`

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
| `extra` | [`Extra8`](../../doc/models/extra-8.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Attempt4 } from 'ps-apimatic-sdk';

const attempt4: Attempt4 = {
  clientIp: '103.59.75.41, 162.158.88.44, 130.176.93.146',
  type: 'execute',
  paymentMethod: 'INTERAC-ETRANSFER',
  flow: 'payform',
  successful: true,
  country: 'INTERAC-ETRANSFER',
  processingTime: 1743769855,
  extra: {
    amount: 1,
    maskedPan: 'INTERAC-ETRANSFER',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

