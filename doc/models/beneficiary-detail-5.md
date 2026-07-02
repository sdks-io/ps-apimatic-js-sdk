
# Beneficiary Detail 5

*This model accepts additional fields of type unknown.*

## Structure

`BeneficiaryDetail5`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `upi` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { BeneficiaryDetail5 } from 'ps-apimatic-sdk';

const beneficiaryDetail5: BeneficiaryDetail5 = {
  upi: 'alpha@bravo',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

