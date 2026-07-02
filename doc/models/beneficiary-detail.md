
# Beneficiary Detail

*This model accepts additional fields of type unknown.*

## Structure

`BeneficiaryDetail`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bankAccountNumber` | `string` | Required | - |
| `upi` | `string` | Required | - |
| `transferType` | `string` | Required | - |
| `ifscCode` | `string` | Required | - |
| `payeeName` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { BeneficiaryDetail } from 'ps-apimatic-sdk';

const beneficiaryDetail: BeneficiaryDetail = {
  bankAccountNumber: '123456789011',
  upi: 'charles.babbage@okhdfc',
  transferType: 'IMPS',
  ifscCode: 'SBIN0001077',
  payeeName: 'deepak singhal',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

