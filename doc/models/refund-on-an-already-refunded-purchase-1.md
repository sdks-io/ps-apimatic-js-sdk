
# Refund on an Already Refunded Purchase 1

*This model accepts additional fields of type unknown.*

## Structure

`RefundOnAnAlreadyRefundedPurchase1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `code` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { RefundOnAnAlreadyRefundedPurchase1 } from 'ps-apimatic-sdk';

const refundOnAnAlreadyRefundedPurchase1: RefundOnAnAlreadyRefundedPurchase1 = {
  message: 'Purchase has already been fully refunded',
  code: 'transaction_error',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

