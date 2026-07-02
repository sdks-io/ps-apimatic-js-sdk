
# Refund on Failed or Pending Transactions 1

*This model accepts additional fields of type unknown.*

## Structure

`RefundOnFailedOrPendingTransactions1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `code` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { RefundOnFailedOrPendingTransactions1 } from 'ps-apimatic-sdk';

const refundOnFailedOrPendingTransactions1: RefundOnFailedOrPendingTransactions1 = {
  message: 'Only Purchases with `status == (paid)` can be refunded.',
  code: 'transaction_error',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

