
# Create Purchase

*This model accepts additional fields of type unknown.*

## Structure

`CreatePurchase`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `code` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreatePurchase } from 'ps-apimatic-sdk';

const createPurchase: CreatePurchase = {
  message: 'Error Message',
  code: 'error_code',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

