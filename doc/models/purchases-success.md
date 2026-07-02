
# Purchases Success

*This model accepts additional fields of type unknown.*

## Structure

`PurchasesSuccess`

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
| `payment` | [`Payment`](../../doc/models/payment.md) | Required | - |
| `issuerDetails` | [`IssuerDetails1`](../../doc/models/issuer-details-1.md) | Required | - |
| `transactionData` | [`TransactionData2`](../../doc/models/transaction-data-2.md) | Required | - |
| `status` | `string` | Required | - |
| `statusHistory` | [`StatusHistory[]`](../../doc/models/status-history.md) | Required | - |
| `viewedOn` | `number` | Required | - |
| `isTest` | `boolean` | Required | - |
| `brandId` | `string` | Required | - |
| `merchantRef` | `string` | Required | - |
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
import { PurchasesSuccess } from 'ps-apimatic-sdk';

const purchasesSuccess: PurchasesSuccess = {
  purchaseId: '64bfdb7df63e36669499e82f',
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
  updatedOn: 1690296521,
  type: 'purchase',
  forceRecurring: false,
  createdOn: 1690295168,
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'dk',
        quantity: 1,
        price: 9,
        discount: 0,
        taxPercent: '0.00',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    total: 9,
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
  payment: {
    isOutgoing: false,
    paymentType: 'PURCHASE',
    amount: 9,
    currency: 'USD',
    netAmount: 9,
    feeAmount: 10.2591,
    pendingAmount: 0,
    pendingUnfreezeOn: 'pending_unfreeze_on2',
    description: '',
    paidOn: 1690295205,
    remotePaidOn: 1690295205,
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
      amount: 9,
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
        successful: true,
        country: 'US',
        processingTime: 1690295205,
        extra: {
          expiryMonth: '10',
          amount: 9,
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
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  status: 'PAID',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1690295168,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'pending_execute',
      timestamp: 1690295193,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'payment_in_process',
      timestamp: 1690295205,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'paid',
      timestamp: 1690296521,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'viewed',
      timestamp: 1690299929,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  viewedOn: 1690299929,
  isTest: false,
  brandId: 'bd69e8a5-adcf-40de-9e43-2b87cb129a5e',
  merchantRef: 'd9db7ec0-f94c-4a9d-8883-54c19c222d81',
  sendReceipt: false,
  isRecurringToken: false,
  skipCapture: false,
  referenceGenerated: 'PS192',
  issued: '2023-07-25',
  due: 1690295168,
  refundUpto: 1705843623,
  ccDescriptor: 'test-cardeye',
  refundAvailability: 'NONE',
  refundableAmount: 9,
  successRedirect: 'https://google.com',
  failureRedirect: 'https://yahoo.com',
  cancelRedirect: '',
  successCallback: '',
  platform: 'API',
  createdFromIp: '149.86.53.48',
  checkoutUrl: 'http://18.214.100.20/payments/64bfdb7df63e36669499e82f/',
  directPostUrl: 'http://18.214.100.20/api/v1/p/64bfdb7df63e36669499e82f/',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

