
# Issuer Details 11

*This model accepts additional fields of type unknown.*

## Structure

`IssuerDetails11`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bankAccounts` | [`BankAccount[]`](../../doc/models/bank-account.md) | Required | - |
| `legalName` | `string` | Required | - |
| `brandName` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { IssuerDetails11 } from 'ps-apimatic-sdk';

const issuerDetails11: IssuerDetails11 = {
  bankAccounts: [
    {
      bankAccount: '',
      bankCode: '',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  legalName: 'newbrand',
  brandName: 'newbrand',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

