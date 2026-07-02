
# Success 47

*This model accepts additional fields of type unknown.*

## Structure

`Success47`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Required | - |
| `client` | [`Client52`](../../doc/models/client-52.md) | Required | - |
| `updatedOn` | `number` | Required | - |
| `type` | `string` | Required | - |
| `paymentMethod` | `string` | Required | - |
| `amountUnit` | `string` | Required | - |
| `errorMsg` | `string` | Required | - |
| `errorCode` | `string` | Required | - |
| `forceRecurring` | `boolean` | Required | - |
| `createdOn` | `number` | Required | - |
| `merchantRef` | `string` | Required | - |
| `purchase` | [`Purchase1`](../../doc/models/purchase-1.md) | Required | - |
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
| `extraFee` | `string` | Required | - |
| `paidOn` | `number` | Required | - |
| `receivedAmt` | `number` | Required | - |
| `taxAmount` | `number` | Required | - |
| `surcharge` | `number` | Required | - |
| `surchargeType` | `string` | Required | - |
| `sessionId` | `string` | Required | - |
| `refundAvailability` | `string` | Required | - |
| `refundableAmount` | `number` | Required | - |
| `successRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `cancelRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `platform` | `string` | Required | - |
| `createdFromIp` | `string` | Required | - |
| `checkoutUrl` | `string` | Required | - |
| `directPostUrl` | `string` | Required | - |
| `payoutProcess` | `boolean` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success47 } from 'ps-apimatic-sdk';

const success47: Success47 = {
  purchaseId: '69b32e42250ac73495aefd50',
  client: {
    customerId: 'NA',
    email: 'himanshu1@paysecure.net',
    fullName: 'OpHM',
    dateOfBirth: '1800-01-01',
    streetAddress: 'SB-124',
    country: 'BR',
    city: 'DLJPR',
    zipCode: '110001',
    cc: [],
    bcc: [],
    stateCode: 'DL',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1773350466,
  type: 'purchase',
  paymentMethod: 'MASTER',
  amountUnit: 'MAJOR',
  errorMsg: '',
  errorCode: 'NA',
  forceRecurring: false,
  createdOn: 1773350466,
  merchantRef: '69b32e42250ac73495aefd50',
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'e-commerce',
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
    requestAmount: 10,
    language: 'en',
    notes: '',
    debt: 0,
    totalFormatted: 1,
    taxAmount: 0,
    taxPercent: 0,
    requestClientDetails: [],
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
    legalName: 'brand',
    brandName: 'brand',
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
      timestamp: 1773350466,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  isTest: false,
  brandId: '5949f2ac-b5a3-4ee4-b585-ad4cf9a6db18',
  sendReceipt: false,
  isRecurringToken: false,
  skipCapture: false,
  referenceGenerated: 'PS1060',
  issued: '2026-03-12',
  due: 1773350466,
  refundUpto: 0,
  ccDescriptor: '',
  fraudScore: 'NA',
  trustScore: 'NA',
  extraFee: '0',
  paidOn: 0,
  receivedAmt: 0,
  taxAmount: 0,
  surcharge: 0,
  surchargeType: '',
  sessionId: '',
  refundAvailability: 'NONE',
  refundableAmount: 0,
  successRedirect: 'https://google.com/',
  failureRedirect: 'https://facebook.com/',
  pendingRedirect: 'https://paysecure.net',
  cancelRedirect: '',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  platform: 'API',
  createdFromIp: '110.235.229.171',
  checkoutUrl: 'https://api.choicepay.ca/payments/1b73d31d178113798afa0157c8805ef0/',
  directPostUrl: 'https://api.choicepay.ca/api/v1/p/69b32e42250ac73495aefd50/',
  payoutProcess: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

