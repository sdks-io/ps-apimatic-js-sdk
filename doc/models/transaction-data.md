
# Transaction Data

*This model accepts additional fields of type unknown.*

## Structure

`TransactionData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentMethod` | `string` | Required | - |
| `flow` | `string` | Required | - |
| `extra` | `unknown` | Required | - |
| `country` | `string` | Required | - |
| `attempts` | `string[]` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { TransactionData } from 'ps-apimatic-sdk';

const transactionData: TransactionData = {
  paymentMethod: '',
  flow: 'payform',
  extra: {  },
  country: '',
  attempts: [],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

