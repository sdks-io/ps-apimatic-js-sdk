
# Refund Amt Exceeds Purchase Amt 1

*This model accepts additional fields of type unknown.*

## Structure

`RefundAmtExceedsPurchaseAmt1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `code` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { RefundAmtExceedsPurchaseAmt1 } from 'ps-apimatic-sdk';

const refundAmtExceedsPurchaseAmt1: RefundAmtExceedsPurchaseAmt1 = {
  message: 'Refund amount exceeds refundable amount',
  code: 'validation_error',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

