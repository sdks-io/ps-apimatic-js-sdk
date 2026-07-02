
# Beneficiary Detail 3

*This model accepts additional fields of type unknown.*

## Structure

`BeneficiaryDetail3`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bankAccountName` | `string` | Required | - |
| `bankAccountNumber` | `string` | Required | - |
| `bankName` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { BeneficiaryDetail3 } from 'ps-apimatic-sdk';

const beneficiaryDetail3: BeneficiaryDetail3 = {
  bankAccountName: 'Rahul Agarwal',
  bankAccountNumber: '645101511808',
  bankName: 'ICICI Bank',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

