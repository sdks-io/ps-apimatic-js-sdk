
# Transaction Already Refunded 1

*This model accepts additional fields of type unknown.*

## Structure

`TransactionAlreadyRefunded1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `code` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { TransactionAlreadyRefunded1 } from 'ps-apimatic-sdk';

const transactionAlreadyRefunded1: TransactionAlreadyRefunded1 = {
  message: 'Transaction cannot be cancelled in status: refunded',
  code: 'transaction_error',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

