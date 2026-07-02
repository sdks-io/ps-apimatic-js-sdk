
# Issuer Details

*This model accepts additional fields of type unknown.*

## Structure

`IssuerDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `website` | `string` | Required | - |
| `legalStreetAddress` | `string` | Required | - |
| `legalCountry` | `string` | Required | - |
| `legalCity` | `string` | Required | - |
| `legalZipCode` | `string` | Required | - |
| `bankAccounts` | `unknown[]` | Required | - |
| `legalName` | `string` | Required | - |
| `brandName` | `string` | Required | - |
| `registrationNumber` | `string` | Required | - |
| `taxNumber` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { IssuerDetails } from 'ps-apimatic-sdk';

const issuerDetails: IssuerDetails = {
  website: '',
  legalStreetAddress: '',
  legalCountry: '',
  legalCity: '',
  legalZipCode: '',
  bankAccounts: [
    {  }
  ],
  legalName: 'Final_cashier',
  brandName: 'Final_cashier',
  registrationNumber: '',
  taxNumber: '',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

