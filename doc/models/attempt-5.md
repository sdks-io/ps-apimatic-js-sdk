
# Attempt 5

*This model accepts additional fields of type unknown.*

## Structure

`Attempt5`

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
| `extra` | [`Extra10`](../../doc/models/extra-10.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Attempt5 } from 'ps-apimatic-sdk';

const attempt5: Attempt5 = {
  clientIp: '103.59.75.42, 172.71.186.102, 130.176.183.14',
  type: 'execute',
  paymentMethod: 'INTERAC-ETRANSFER',
  flow: 'payform',
  successful: true,
  country: 'INTERAC',
  processingTime: 1737549663,
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

