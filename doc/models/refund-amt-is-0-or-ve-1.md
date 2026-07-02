
# Refund Amt Is 0 or Ve 1

*This model accepts additional fields of type unknown.*

## Structure

`RefundAmtIs0OrVe1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `code` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { RefundAmtIs0OrVe1 } from 'ps-apimatic-sdk';

const refundAmtIs0OrVe1: RefundAmtIs0OrVe1 = {
  message: 'Refund amount must be greater than 0',
  code: 'validation_error',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

