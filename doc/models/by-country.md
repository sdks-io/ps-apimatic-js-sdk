
# By Country

*This model accepts additional fields of type unknown.*

## Structure

`ByCountry`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `any` | `string[]` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ByCountry } from 'ps-apimatic-sdk';

const byCountry: ByCountry = {
  any: [
    'MASTER',
    'VISA',
    'JCB',
    'AMEX',
    'CRYPTO-BRIDGE',
    'FawryPay',
    'INTERAC-E-TRANSFER',
    'INTERAC-REQUEST-MONEY',
    'MOBILEMONEY',
    'NEOSURF',
    'PAYID',
    'PIX',
    'SPEI',
    'THIRDPARTY-UPI',
    'DISCOVER',
    'BANKTRANSFER',
    'VIRTUAL-IBAN',
    'UPI-COLLECT',
    'UPI-QR',
    'VIRTUAL-ACCOUNT',
    'DINERS',
    'NETBANKING'
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

