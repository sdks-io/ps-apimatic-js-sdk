
# Purchase 73

*This model accepts additional fields of type unknown.*

## Structure

`Purchase73`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Required | - |
| `client` | [`Client2`](../../doc/models/client-2.md) | Required | - |
| `updatedOn` | `number` | Required | - |
| `type` | `string` | Required | - |
| `forceRecurring` | `boolean` | Required | - |
| `createdOn` | `number` | Required | - |
| `purchase` | [`Purchase2`](../../doc/models/purchase-2.md) | Required | - |
| `issuerDetails` | [`IssuerDetails1`](../../doc/models/issuer-details-1.md) | Required | - |
| `transactionData` | [`TransactionData`](../../doc/models/transaction-data.md) | Required | - |
| `status` | `string` | Required | - |
| `statusHistory` | [`StatusHistory[]`](../../doc/models/status-history.md) | Required | - |
| `isTest` | `boolean` | Required | - |
| `brandId` | `string` | Required | - |
| `isRecurringToken` | `boolean` | Required | - |
| `referenceGenerated` | `string` | Required | - |
| `merchantRef` | `string` | Required | - |
| `issued` | `string` | Required | - |
| `due` | `number` | Required | - |
| `refundUpto` | `number` | Required | - |
| `ccDescriptor` | `string` | Required | - |
| `refundAvailability` | `string` | Required | - |
| `refundableAmount` | `number` | Required | - |
| `successRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `cancelRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `platform` | `string` | Required | - |
| `createdFromIp` | `string` | Required | - |
| `checkoutUrl` | `string` | Required | - |
| `directPostUrl` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Purchase73 } from 'ps-apimatic-sdk';

const purchase73: Purchase73 = {
  purchaseId: '64b032c3c6dccf7d329d9e7e',
  client: {
    bankAccount: '',
    bankCode: '',
    email: 'dev@paysecure.net',
    phone: '',
    fullName: '',
    dateOfBirth: '',
    personalCode: '',
    streetAddress: 'test test',
    country: 'IN',
    city: '123',
    zipCode: '234567',
    shippingStreetAddress: '',
    shippingCountry: '',
    shippingCity: '',
    shippingZipCode: '',
    cc: [],
    bcc: [],
    legalName: '',
    brandName: '',
    registrationNumber: '',
    taxNumber: '',
    stateCode: 'ca',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1689268934,
  type: 'purchase',
  forceRecurring: false,
  createdOn: 1689268934,
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'dk',
        quantity: 1,
        price: 10,
        discount: 0,
        taxPercent: '0.00',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    total: 10,
    language: 'en',
    notes: '',
    debt: 0,
    totalFormatted: 1,
    requestClientDetails: [],
    timezone: 'America/Edmonton',
    emailMessage: '',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  issuerDetails: {
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
  },
  transactionData: {
    paymentMethod: '',
    flow: 'payform',
    extra: {  },
    country: '',
    attempts: [],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  status: 'CREATED',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1689268934,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  isTest: false,
  brandId: 'bd69e8a5-adcf-40de-9e43-2b87cb129a5e',
  isRecurringToken: false,
  referenceGenerated: 'PS161',
  merchantRef: 'd9db7ec0-f94c-4a9d-8883-54c19c222d81',
  issued: '2023-07-13',
  due: 1689268934,
  refundUpto: 0,
  ccDescriptor: '',
  refundAvailability: 'NONE',
  refundableAmount: 0,
  successRedirect: 'https://your.success.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  cancelRedirect: '',
  successCallback: '',
  platform: 'API',
  createdFromIp: '149.86.53.48',
  checkoutUrl: 'http://18.214.100.20/payments/64b032c3c6dccf7d329d9e7e/',
  directPostUrl: 'http://18.214.100.20/api/v1/p/64b032c3c6dccf7d329d9e7e/',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

