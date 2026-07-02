
# Beneficiary Detail 1

*This model accepts additional fields of type unknown.*

## Structure

`BeneficiaryDetail1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bankAccountName` | `string` | Required | - |
| `bankAccountNumber` | `string` | Required | - |
| `ifscCode` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { BeneficiaryDetail1 } from 'ps-apimatic-sdk';

const beneficiaryDetail1: BeneficiaryDetail1 = {
  bankAccountName: 'Rahul Jain',
  bankAccountNumber: '123456789012',
  ifscCode: 'HDFC021212',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

