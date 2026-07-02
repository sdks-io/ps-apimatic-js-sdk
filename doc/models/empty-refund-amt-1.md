
# Empty Refund Amt 1

*This model accepts additional fields of type unknown.*

## Structure

`EmptyRefundAmt1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `code` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { EmptyRefundAmt1 } from 'ps-apimatic-sdk';

const emptyRefundAmt1: EmptyRefundAmt1 = {
  message: 'Amount is required',
  code: 'validation_error',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

