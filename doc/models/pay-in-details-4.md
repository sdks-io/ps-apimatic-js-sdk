
# Pay in Details 4

*This model accepts additional fields of type unknown.*

## Structure

`PayInDetails4`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `referenceNumber` | `string` | Required | - |
| `paymentMethod` | `string` | Required | - |
| `transactionExpiry` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PayInDetails4 } from 'ps-apimatic-sdk';

const payInDetails4: PayInDetails4 = {
  referenceNumber: '9350804722',
  paymentMethod: 'PAYATFAWRY',
  transactionExpiry: '29 Jun 2024 05:39:59:054 +0000',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

