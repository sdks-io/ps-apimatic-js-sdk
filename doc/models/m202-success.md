
# M202 Success

*This model accepts additional fields of type unknown.*

## Structure

`M202Success`

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
| `errorCode` | `string` | Required | - |
| `savedCardUsed` | `string` | Required | - |
| `redirectType` | `string` | Required | - |
| `forceRecurring` | `boolean` | Required | - |
| `createdOn` | `number` | Required | - |
| `merchantRef` | `string` | Required | - |
| `merchantName` | `string` | Required | - |
| `merchantType` | `string` | Required | - |
| `purchase` | [`Purchase1`](../../doc/models/purchase-1.md) | Required | - |
| `issuerDetails` | [`IssuerDetails`](../../doc/models/issuer-details.md) | Required | - |
| `transactionData` | [`TransactionData37`](../../doc/models/transaction-data-37.md) | Required | - |
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
| `checkoutUrl` | `string` | Required | - |
| `directPostUrl` | `string` | Required | - |
| `payoutProcess` | `boolean` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { M202Success } from 'ps-apimatic-sdk';

const m202Success: M202Success = {
  purchaseId: '6950e4e3e4a1b008c2fae5c3',
  client: {
    customerId: '69034a5a61b460084d20c23b',
    email: 'rahul+23@paysecure.net',
    phone: '+919634088561',
    fullName: 'Rahul Agarwal',
    streetAddress: 'Vaishali Jaipur',
    country: 'NA',
    city: 'jaipur',
    zipCode: '202020',
    cc: [],
    bcc: [],
    stateCode: 'RA',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1766909180,
  type: 'purchase',
  paymentMethod: 'MASTER,VISA,JCB,AMEX,CRYPTO-BRIDGE,FawryPay,INTERAC-E-TRANSFER,INTERAC-REQUEST-MONEY,MOBILEMONEY,NEOSURF,PAYID,PIX,SPEI,THIRDPARTY-UPI,DISCOVER,BANKTRANSFER,VIRTUAL-IBAN,UPI-COLLECT,UPI-QR,VIRTUAL-ACCOUNT,DINERS,NETBANKING,THIRDPARTY-NETBANKING,MAYA,GCASH,INTERAC-EXPRESS,QRPH',
  amountUnit: 'MAJOR',
  errorMsg: 'This customer can not be processed !',
  errorCode: 'NA',
  savedCardUsed: 'NO',
  redirectType: 'POST',
  forceRecurring: false,
  createdOn: 1766909155,
  merchantRef: '6950e4e3e4a1b008c2fae5c3',
  merchantName: 'rahul_test',
  merchantType: 'MERCHANT',
  purchase: {
    currency: 'EUR',
    products: [
      {
        name: 'NA',
        quantity: 1,
        price: 22,
        discount: 0,
        taxPercent: '0.00',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    total: 22,
    requestAmount: 22,
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
    legalName: 'Testing',
    brandName: 'Testing',
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
      expiryMonth: '07',
      amount: 22,
      cardIssuer: 'CIAGROUP',
      maskedPan: '55555555****4444',
      cardBrand: 'MASTER',
      cardIssuerCountry: 'BR',
      cardType: 'DEBIT',
      cardholderName: 'rahul',
      expiryYear: '30',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    country: '',
    attempts: [
      {
        clientIp: '183.83.53.214',
        type: 'execute',
        paymentMethod: 'MASTER',
        flow: 'payform',
        successful: false,
        country: 'BR',
        processingTime: 1766909179,
        extra: {
          expiryMonth: '07',
          amount: 22,
          cardIssuer: 'CIAGROUP',
          maskedPan: '55555555****4444',
          cardBrand: 'MASTER',
          cardIssuerCountry: 'BR',
          cardType: 'DEBIT',
          cardholderName: 'rahul',
          expiryYear: '30',
          additionalProperties: {
            'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
          },
        },
        error: {
          message: 'This customer can not be processed !',
          code: 'no_mid_found',
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
      timestamp: 1766909155,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'pending_execute',
      timestamp: 1766909179,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'error',
      timestamp: 1766909180,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'viewed',
      timestamp: 1766909186,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  viewedOn: 1766909186,
  isTest: false,
  brandId: '59c5ed48-caf9-464a-ba54-26e1e02bc1bc',
  sendReceipt: false,
  isRecurringToken: false,
  skipCapture: false,
  referenceGenerated: 'PS334',
  issued: '2025-12-28',
  due: 1766909155,
  refundUpto: 0,
  ccDescriptor: '',
  fraudScore: '0',
  trustScore: '0',
  extraFee: '0',
  paidOn: 0,
  receivedAmt: 0,
  taxAmount: 0,
  surcharge: 0,
  surchargeType: '',
  sessionId: '6950e4ba5205280b71ac2010',
  refundAvailability: 'NONE',
  refundableAmount: 0,
  successRedirect: 'https://google.com/',
  failureRedirect: 'https://google.com/',
  pendingRedirect: 'https://google.com/',
  cancelRedirect: '',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  platform: 'API',
  checkoutUrl: 'https://api.choicepay.ca/payments/adb6e07f74ec6197ef764909736d478e/',
  directPostUrl: 'https://api.choicepay.ca/api/v1/p/6950e4e3e4a1b008c2fae5c3/',
  payoutProcess: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

