
# Payment Method Success

*This model accepts additional fields of type unknown.*

## Structure

`PaymentMethodSuccess`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `availablePaymentMethods` | `string[]` | Required | - |
| `byCountry` | [`ByCountry`](../../doc/models/by-country.md) | Required | - |
| `countryNames` | [`CountryNames`](../../doc/models/country-names.md) | Required | - |
| `names` | [`Names`](../../doc/models/names.md) | Required | - |
| `cardMethods` | `string[]` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PaymentMethodSuccess } from 'ps-apimatic-sdk';

const paymentMethodSuccess: PaymentMethodSuccess = {
  availablePaymentMethods: [
    'MASTER',
    'visa',
    'jcb',
    'amex',
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
    'discover',
    'BANKTRANSFER',
    'VIRTUAL-IBAN',
    'UPI-COLLECT',
    'UPI-QR',
    'VIRTUAL-ACCOUNT',
    'DINERS',
    'NETBANKING'
  ],
  byCountry: {
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
  },
  countryNames: {
    any: 'Other',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  names: {
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
  },
  cardMethods: [
    'MASTER',
    'VISA',
    'JCB',
    'AMEX',
    'DISCOVER'
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

