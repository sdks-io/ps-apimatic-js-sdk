
# Extra 10

*This model accepts additional fields of type unknown.*

## Structure

`Extra10`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `amount` | `number` | Required | - |
| `maskedPan` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Extra10 } from 'ps-apimatic-sdk';

const extra10: Extra10 = {
  amount: 1,
  maskedPan: 'INTERAC-ETRANSFER',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

