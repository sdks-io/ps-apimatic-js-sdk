
# Purchase Error

*This model accepts additional fields of type unknown.*

## Structure

`PurchaseError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `code` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PurchaseError } from 'ps-apimatic-sdk';

const purchaseError: PurchaseError = {
  message: 'Brand not found!',
  code: 'transaction_error',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

