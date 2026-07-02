
# Success 17

*This model accepts additional fields of type unknown.*

## Structure

`Success17`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Required | - |
| `client` | [`Client70`](../../doc/models/client-70.md) | Required | - |
| `updatedOn` | `number` | Required | - |
| `type` | `string` | Required | - |
| `paymentMethod` | `string` | Required | - |
| `amountUnit` | `string` | Required | - |
| `errorMsg` | `string` | Required | - |
| `redirectType` | `string` | Required | - |
| `forceRecurring` | `boolean` | Required | - |
| `createdOn` | `number` | Required | - |
| `merchantRef` | `string` | Required | - |
| `merchantName` | `string` | Required | - |
| `purchase` | [`Purchase47`](../../doc/models/purchase-47.md) | Required | - |
| `issuerDetails` | [`IssuerDetails`](../../doc/models/issuer-details.md) | Required | - |
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
| `fraudScore` | `string` | Required | - |
| `trustScore` | `string` | Required | - |
| `paidOn` | `number` | Required | - |
| `refundAvailability` | `string` | Required | - |
| `refundableAmount` | `number` | Required | - |
| `successRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `cancelRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `platform` | `string` | Required | - |
| `createdFromIp` | `string` | Required | - |
| `checkoutUrl` | `string` | Required | - |
| `payoutProcess` | `boolean` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success17 } from 'ps-apimatic-sdk';

const success17: Success17 = {
  purchaseId: '68441c2a7559cf659fd7e835',
  client: {
    customerId: 'NA',
    email: 'arun44@gmail.com',
    phone: '+237679544810',
    fullName: 'Olive Tsafack',
    streetAddress: 'test test',
    country: 'AU',
    city: '123',
    zipCode: '234567',
    cc: [],
    bcc: [],
    stateCode: 'ca',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1749294123,
  type: 'purchase',
  paymentMethod: 'PAYID',
  amountUnit: 'MAJOR',
  errorMsg: '',
  redirectType: 'POST',
  forceRecurring: false,
  createdOn: 1749294123,
  merchantRef: '68441c2a7559cf659fd7e835',
  merchantName: 'Merchant002',
  purchase: {
    currency: 'AUD',
    products: [
      {
        name: 'test',
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
    taxAmount: 0,
    taxPercent: 0,
    requestClientDetails: [],
    timezone: 'MIT',
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
      {  }
    ],
    legalName: '44',
    brandName: '44',
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
      timestamp: 1749294123,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  isTest: false,
  brandId: 'c4003b2c-22d4-4dc1-ad0c-c6b54f8c9636',
  sendReceipt: false,
  isRecurringToken: false,
  skipCapture: false,
  referenceGenerated: 'PS19963',
  issued: '2025-06-07',
  due: 1749294123,
  refundUpto: 0,
  ccDescriptor: '',
  fraudScore: 'NA',
  trustScore: 'NA',
  paidOn: 0,
  refundAvailability: 'NONE',
  refundableAmount: 0,
  successRedirect: '<https://your.redirect.url/getResponse.jsp?success=true>',
  failureRedirect: '<https://your.redirect.url/getResponse.jsp?success=false>',
  cancelRedirect: '',
  successCallback: '<https://webhook.site/ec813a7a-4dd1-4aa3-99f3-f01637ab224c>',
  failureCallback: '<https://webhook.site/ec813a7a-4dd1-4aa3-99f3-f01637ab224c>',
  platform: 'API',
  createdFromIp: '183.83.54.51',
  checkoutUrl: '<https://staging.paysecure.net/payments/68441c2a7559cf659fd7e835/>',
  payoutProcess: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

