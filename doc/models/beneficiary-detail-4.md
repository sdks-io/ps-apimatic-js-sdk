
# Beneficiary Detail 4

*This model accepts additional fields of type unknown.*

## Structure

`BeneficiaryDetail4`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bankName` | `string` | Required | - |
| `bankAccountName` | `string` | Required | - |
| `bankAccountCurrency` | `string` | Required | - |
| `bankAccountNumber` | `string` | Required | - |
| `bankCountryCode` | `string` | Required | - |
| `swiftCode` | `string` | Required | - |
| `routingParam` | [`RoutingParam`](../../doc/models/routing-param.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { BeneficiaryDetail4 } from 'ps-apimatic-sdk';

const beneficiaryDetail4: BeneficiaryDetail4 = {
  bankName: 'DBS Bank',
  bankAccountName: 'test test',
  bankAccountCurrency: 'SGD',
  bankAccountNumber: '12345640',
  bankCountryCode: 'SG',
  swiftCode: 'DBSSSGSG',
  routingParam: {
    bankCode: '897678',
    bankBranchCode: '888',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

