
# Refund Exceeds Remaining Balance after a Partial Refund 1

*This model accepts additional fields of type unknown.*

## Structure

`RefundExceedsRemainingBalanceAfterAPartialRefund1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `code` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import {
  RefundExceedsRemainingBalanceAfterAPartialRefund1,
} from 'ps-apimatic-sdk';

const refundExceedsRemainingBalanceAfterAPartialRefund1: RefundExceedsRemainingBalanceAfterAPartialRefund1 = {
  message: 'Refund amount exceeds refundable amount: 2.0',
  code: 'validation_error',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

