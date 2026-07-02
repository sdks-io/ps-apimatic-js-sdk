
# Success 2

*This model accepts additional fields of type unknown.*

## Structure

`Success2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Required | - |
| `client` | [`Client6`](../../doc/models/client-6.md) | Required | - |
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
import { Success2 } from 'ps-apimatic-sdk';

const success2: Success2 = {
  purchaseId: '64bff4fff63e36669499e9c8',
  client: {
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
  updatedOn: 1690301735,
  type: 'purchase',
  forceRecurring: false,
  createdOn: 1690301698,
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
  status: 'CANCELLED',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1690301698,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'pending_execute',
      timestamp: 1690301723,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'cancelled',
      timestamp: 1690301735,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  isTest: false,
  brandId: 'bd69e8a5-adcf-40de-9e43-2b87cb129a5e',
  sendReceipt: false,
  isRecurringToken: false,
  skipCapture: false,
  referenceGenerated: 'PS194',
  issued: '2023-07-25',
  due: 1690301698,
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
  checkoutUrl: 'http://18.214.100.20/payments/64bff4fff63e36669499e9c8/',
  directPostUrl: 'http://18.214.100.20/api/v1/p/64bff4fff63e36669499e9c8/',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

