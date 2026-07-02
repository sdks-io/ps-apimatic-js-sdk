
# Beneficiary Detail 6

*This model accepts additional fields of type unknown.*

## Structure

`BeneficiaryDetail6`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `upi` | `string` | Required | - |
| `transferType` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { BeneficiaryDetail6 } from 'ps-apimatic-sdk';

const beneficiaryDetail6: BeneficiaryDetail6 = {
  upi: 'charles.babbage@okhdfc',
  transferType: 'UPI',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

