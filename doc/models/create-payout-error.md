
# Create Payout Error

*This model accepts additional fields of type unknown.*

## Structure

`CreatePayoutError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `code` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreatePayoutError } from 'ps-apimatic-sdk';

const createPayoutError: CreatePayoutError = {
  message: 'Insufficient Balance [5.23]',
  code: 'transaction_error',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

