
# Extra 8

*This model accepts additional fields of type unknown.*

## Structure

`Extra8`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `amount` | `number` | Required | - |
| `maskedPan` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Extra8 } from 'ps-apimatic-sdk';

const extra8: Extra8 = {
  amount: 1,
  maskedPan: 'INTERAC-ETRANSFER',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

