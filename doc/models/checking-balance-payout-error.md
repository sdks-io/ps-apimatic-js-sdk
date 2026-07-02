
# Checking Balance Payout Error

*This model accepts additional fields of type unknown.*

## Structure

`CheckingBalancePayoutError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `code` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CheckingBalancePayoutError } from 'ps-apimatic-sdk';

const checkingBalancePayoutError: CheckingBalancePayoutError = {
  message: 'Error Message',
  code: 'No currency account found',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

