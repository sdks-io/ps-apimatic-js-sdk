
# Invalid Purchase Id 1

*This model accepts additional fields of type unknown.*

## Structure

`InvalidPurchaseId1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `code` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { InvalidPurchaseId1 } from 'ps-apimatic-sdk';

const invalidPurchaseId1: InvalidPurchaseId1 = {
  message: 'Transaction not found',
  code: 'transaction_error',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

