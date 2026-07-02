
# Names

*This model accepts additional fields of type unknown.*

## Structure

`Names`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `netbanking` | `string` | Required | - |
| `amex` | `string` | Required | - |
| `master` | `string` | Required | - |
| `cryptoBridge` | `string` | Required | - |
| `payid` | `string` | Required | - |
| `spei` | `string` | Required | - |
| `discover` | `string` | Required | - |
| `jcb` | `string` | Required | - |
| `visa` | `string` | Required | - |
| `neosurf` | `string` | Required | - |
| `interacETransfer` | `string` | Required | - |
| `thirdpartyUpi` | `string` | Required | - |
| `virtualIban` | `string` | Required | - |
| `banktransfer` | `string` | Required | - |
| `diners` | `string` | Required | - |
| `interacRequestMoney` | `string` | Required | - |
| `upiCollect` | `string` | Required | - |
| `upiQr` | `string` | Required | - |
| `mobilemoney` | `string` | Required | - |
| `fawryPay` | `string` | Required | - |
| `virtualAccount` | `string` | Required | - |
| `pix` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Names } from 'ps-apimatic-sdk';

const names: Names = {
  netbanking: 'NETBANKING',
  amex: 'AMEX',
  master: 'Mastercard',
  cryptoBridge: 'CRYPTO-BRIDGE',
  payid: 'PAYID',
  spei: 'SPEI',
  discover: 'DISCOVER',
  jcb: 'JCB',
  visa: 'Visa',
  neosurf: 'NEOSURF',
  interacETransfer: 'INTERAC-E-TRANSFER',
  thirdpartyUpi: 'THIRDPARTY-UPI',
  virtualIban: 'VIRTUAL-IBAN',
  banktransfer: 'BANKTRANSFER',
  diners: 'DINERS',
  interacRequestMoney: 'INTERAC-REQUEST-MONEY',
  upiCollect: 'UPI-COLLECT',
  upiQr: 'UPI-QR',
  mobilemoney: 'MOBILEMONEY',
  fawryPay: 'FawryPay',
  virtualAccount: 'VIRTUAL-ACCOUNT',
  pix: 'PIX',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

