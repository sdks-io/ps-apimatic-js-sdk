
# Checking Balance Request

*This model accepts additional fields of type unknown.*

## Structure

`CheckingBalanceRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentMethod` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CheckingBalanceRequest } from 'ps-apimatic-sdk';

const checkingBalanceRequest: CheckingBalanceRequest = {
  paymentMethod: 'INTERAC-ETRANSFER',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

