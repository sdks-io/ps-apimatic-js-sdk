
# Balance 1

*This model accepts additional fields of type unknown.*

## Structure

`Balance1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currency` | `string \| undefined` | Optional | - |
| `balance` | `number \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Balance1 } from 'ps-apimatic-sdk';

const balance1: Balance1 = {
  currency: 'currency2',
  balance: 17.56,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

