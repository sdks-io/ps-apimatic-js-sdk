
# Transaction

*This model accepts additional fields of type unknown.*

## Structure

`Transaction`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `transactionId` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `currency` | `string` | Required | - |
| `createdDate` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Transaction } from 'ps-apimatic-sdk';

const transaction: Transaction = {
  transactionId: '69d79150aa6d618c9b4e5da1',
  amount: 1,
  currency: 'GBP',
  createdDate: 1775735120,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

