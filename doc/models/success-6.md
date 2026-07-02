
# Success 6

*This model accepts additional fields of type unknown.*

## Structure

`Success6`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currency` | `string` | Required | - |
| `balance` | `string` | Required | - |
| `paymentMethod` | `string` | Required | - |
| `status` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success6 } from 'ps-apimatic-sdk';

const success6: Success6 = {
  currency: 'CAD',
  balance: '2.22',
  paymentMethod: 'INTERAC-REQUEST-MONEY',
  status: 'success',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

