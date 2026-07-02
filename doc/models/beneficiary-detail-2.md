
# Beneficiary Detail 2

*This model accepts additional fields of type unknown.*

## Structure

`BeneficiaryDetail2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bankAccountName` | `string` | Required | - |
| `bankAccountNumber` | `string` | Required | - |
| `bankCountryCode` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { BeneficiaryDetail2 } from 'ps-apimatic-sdk';

const beneficiaryDetail2: BeneficiaryDetail2 = {
  bankAccountName: 'Rahul Agarwal',
  bankAccountNumber: '645101511808',
  bankCountryCode: 'AT',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

