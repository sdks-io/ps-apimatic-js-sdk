
# Partial Refund Api Request

*This model accepts additional fields of type unknown.*

## Structure

`PartialRefundApiRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `amount` | `string` | Required | - |
| `reason` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PartialRefundApiRequest } from 'ps-apimatic-sdk';

const partialRefundApiRequest: PartialRefundApiRequest = {
  amount: '5.12',
  reason: 'Partial Refunds Testing',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

