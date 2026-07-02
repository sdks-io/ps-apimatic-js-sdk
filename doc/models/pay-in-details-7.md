
# Pay in Details 7

*This model accepts additional fields of type unknown.*

## Structure

`PayInDetails7`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `clabe` | `string` | Required | - |
| `beneficiary` | `string` | Required | - |
| `amount` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PayInDetails7 } from 'ps-apimatic-sdk';

const payInDetails7: PayInDetails7 = {
  clabe: '710969000049618169',
  beneficiary: 'CHOICEPAY LTD.',
  amount: '100.00',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

