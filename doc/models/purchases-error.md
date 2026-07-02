
# Purchases Error

*This model accepts additional fields of type unknown.*

## Structure

`PurchasesError`

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
| `transactionData` | [`TransactionData1`](../../doc/models/transaction-data-1.md) | Required | - |
| `status` | `string` | Required | - |
| `statusHistory` | [`StatusHistory[]`](../../doc/models/status-history.md) | Required | - |
| `viewedOn` | `number` | Required | - |
| `isTest` | `boolean` | Required | - |
| `brandId` | `string` | Required | - |
| `sendReceipt` | `boolean` | Required | - |
| `isRecurringToken` | `boolean` | Required | - |
| `skipCapture` | `boolean` | Required | - |
| `referenceGenerated` | `string` | Required | - |
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
import { PurchasesError } from 'ps-apimatic-sdk';

const purchasesError: PurchasesError = {
  purchaseId: '64bfd7c9f63e36669499e779',
  client: {
    bankAccount: '',
    bankCode: '',
    email: 'example@paysecure.net',
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
  updatedOn: 1690294251,
  type: 'purchase',
  forceRecurring: false,
  createdOn: 1690294220,
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'dk',
        quantity: 1,
        price: 100,
        discount: 0,
        taxPercent: '0.00',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    total: 100,
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
    extra: {
      expiryMonth: '10',
      amount: 100,
      cardIssuer: '1-800-432-3117',
      maskedPan: '411111XXXXXX1111',
      cardBrand: 'VISA',
      cardIssuerCountry: 'US',
      cardholderName: 'dk',
      expiryYear: '23',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    country: '',
    attempts: [
      {
        clientIp: '149.86.53.48',
        type: 'execute',
        paymentMethod: 'VISA',
        flow: 'payform',
        successful: false,
        country: 'US',
        processingTime: 1690294279,
        extra: {
          expiryMonth: '10',
          amount: 100,
          cardIssuer: '1-800-432-3117',
          maskedPan: '411111XXXXXX1111',
          cardBrand: 'VISA',
          cardIssuerCountry: 'US',
          cardholderName: 'dk',
          expiryYear: '23',
          additionalProperties: {
            'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
          },
        },
        error: {
          message: 'Transaction Failed',
          code: 'transaction_error',
          additionalProperties: {
            'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
          },
        },
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  status: 'ERROR',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1690294220,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'pending_execute',
      timestamp: 1690294251,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'error',
      timestamp: 1690294299,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'viewed',
      timestamp: 1690294382,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  viewedOn: 1690299845,
  isTest: false,
  brandId: 'bd69e8a5-adcf-40de-9e43-2b87cb129a5e',
  sendReceipt: false,
  isRecurringToken: false,
  skipCapture: false,
  referenceGenerated: 'PS188',
  issued: '2023-07-25',
  due: 1690294220,
  refundUpto: 0,
  ccDescriptor: '',
  refundAvailability: 'NONE',
  refundableAmount: 0,
  successRedirect: 'https://google.com',
  failureRedirect: 'https://yahoo.com',
  cancelRedirect: '',
  successCallback: '',
  platform: 'API',
  createdFromIp: '149.86.53.48',
  checkoutUrl: 'http://18.214.100.20/payments/64bfd7c9f63e36669499e779/',
  directPostUrl: 'http://18.214.100.20/api/v1/p/64bfd7c9f63e36669499e779/',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

