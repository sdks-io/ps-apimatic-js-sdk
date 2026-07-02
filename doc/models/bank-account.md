
# Bank Account

*This model accepts additional fields of type unknown.*

## Structure

`BankAccount`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bankAccount` | `string` | Required | - |
| `bankCode` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { BankAccount } from 'ps-apimatic-sdk';

const bankAccount: BankAccount = {
  bankAccount: '',
  bankCode: '',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

