
# Success

*This model accepts additional fields of type unknown.*

## Structure

`Success`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Required | - |
| `client` | [`Client1`](../../doc/models/client-1.md) | Required | - |
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
| `totalRefunded` | `number` | Required | - |
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
import { Success } from 'ps-apimatic-sdk';

const success: Success = {
  purchaseId: '6a1d26a3d373e5fd3c44ae14',
  client: {
    customerId: 'NA',
    email: 'rahultest@gmail.com',
    phone: '6393000899',
    streetAddress: 'test test',
    country: 'IN',
    city: '123',
    zipCode: '234567',
    cc: [],
    bcc: [],
    stateCode: 'ca',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1780295331,
  type: 'purchase',
  paymentMethod: 'MASTER,VISA,JCB,VIRTUAL-CARD,MOBILEMONEY,UPI-INTENT,UPI-QR,INTERAC-E-TRANSFER,INTERAC-REQUEST-MONEY,INTERAC-EXPRESS,PIX,FawryPay,OPEN-BANKING,SPEI',
  amountUnit: 'MAJOR',
  errorMsg: '',
  errorCode: 'NA',
  forceRecurring: false,
  createdOn: 1780295331,
  merchantRef: 'rahul2345@gmail.co',
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'product name',
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
    legalName: 'Final_cashier',
    brandName: 'Final_cashier',
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
      timestamp: 1780295331,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  isTest: false,
  brandId: '76067f4a-3155-4bf0-872b-a77a382d4cf7',
  sendReceipt: false,
  isRecurringToken: false,
  skipCapture: false,
  referenceGenerated: 'PS1172',
  issued: '2026-06-01',
  due: 1780295331,
  refundUpto: 0,
  ccDescriptor: '',
  fraudScore: 'NA',
  trustScore: 'NA',
  extraFee: '0',
  totalRefunded: 0,
  paidOn: 0,
  receivedAmt: 0,
  taxAmount: 0,
  surcharge: 0,
  surchargeType: '',
  sessionId: '',
  refundAvailability: 'NONE',
  refundableAmount: 0,
  successRedirect: 'https://your.success.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  cancelRedirect: '',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  platform: 'API',
  createdFromIp: '103.80.161.238',
  checkoutUrl: 'https://test4.paymentsclub.net/payments/c3f2eee71c5824b75c7b52ff41e76814/',
  directPostUrl: 'https://test4.paymentsclub.net/api/v1/p/6a1d26a3d373e5fd3c44ae14/',
  payoutProcess: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

