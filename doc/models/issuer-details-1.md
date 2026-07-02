
# Issuer Details 1

*This model accepts additional fields of type unknown.*

## Structure

`IssuerDetails1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `website` | `string` | Required | - |
| `legalStreetAddress` | `string` | Required | - |
| `legalCountry` | `string` | Required | - |
| `legalCity` | `string` | Required | - |
| `legalZipCode` | `string` | Required | - |
| `bankAccounts` | [`BankAccount[]`](../../doc/models/bank-account.md) | Required | - |
| `legalName` | `string` | Required | - |
| `brandName` | `string` | Required | - |
| `registrationNumber` | `string` | Required | - |
| `taxNumber` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { IssuerDetails1 } from 'ps-apimatic-sdk';

const issuerDetails1: IssuerDetails1 = {
  website: '',
  legalStreetAddress: '',
  legalCountry: '',
  legalCity: '',
  legalZipCode: '',
  bankAccounts: [
    {
      bankAccount: '',
      bankCode: '',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  legalName: 'shoes',
  brandName: 'shoes',
  registrationNumber: '',
  taxNumber: '',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

