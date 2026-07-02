
# Purchases Success 5

*This model accepts additional fields of type unknown.*

## Structure

`PurchasesSuccess5`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Required | - |
| `client` | [`Client41`](../../doc/models/client-41.md) | Required | - |
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
| `purchase` | [`Purchase62`](../../doc/models/purchase-62.md) | Required | - |
| `payment` | [`Payment4`](../../doc/models/payment-4.md) | Required | - |
| `issuerDetails` | [`IssuerDetails`](../../doc/models/issuer-details.md) | Required | - |
| `transactionData` | [`TransactionData7`](../../doc/models/transaction-data-7.md) | Required | - |
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
| `payInDetails` | [`PayInDetails10`](../../doc/models/pay-in-details-10.md) | Required | - |
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
import { PurchasesSuccess5 } from 'ps-apimatic-sdk';

const purchasesSuccess5: PurchasesSuccess5 = {
  purchaseId: '66c4667bb993c970367c288a',
  client: {
    email: 'deepakdeepaksinghal@gmail.com',
    dateOfBirth: '1970-07-10',
    streetAddress: '10 New Burlington Street Apt. 214',
    country: 'IN',
    city: 'London',
    zipCode: 'W1S 3BE',
    cc: [],
    bcc: [],
    stateCode: 'QLD',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1724147324,
  type: 'purchase',
  paymentMethod: 'UPI',
  amountUnit: 'MAJOR',
  errorMsg: '',
  redirectType: 'POST',
  forceRecurring: false,
  createdOn: 1724147324,
  merchantRef: '66c4667bb993c970367c288a',
  merchantName: 'merchant002',
  purchase: {
    currency: 'INR',
    products: [
      {
        name: 'test',
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
    expireInMin: '35',
    requestClientDetails: [],
    timezone: 'MIT',
    emailMessage: '',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  payment: {
    isOutgoing: false,
    paymentType: 'PURCHASE',
    amount: 10,
    currency: 'INR',
    netAmount: 10,
    feeAmount: 0,
    pendingAmount: 0,
    pendingUnfreezeOn: 'pending_unfreeze_on2',
    description: '',
    paidOn: 1724147324,
    remotePaidOn: 1724147324,
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
    legalName: 'test6',
    brandName: 'test6',
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
      amount: 10,
      maskedPan: 'UPI',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    country: '',
    attempts: [
      {
        clientIp: '103.59.75.113',
        type: 'execute',
        paymentMethod: 'UPI',
        flow: 'payform',
        successful: true,
        country: 'UPI',
        processingTime: 1724147324,
        extra: {
          amount: 10,
          maskedPan: 'UPI',
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
  status: 'PAYMENT_IN_PROCESS',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1724147324,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'pending_execute',
      timestamp: 1724147324,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'payment_in_process',
      timestamp: 1724147324,
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
  referenceGenerated: 'PS10907',
  issued: '2024-08-20',
  due: 1724147324,
  refundUpto: 1725871728,
  ccDescriptor: 'test1',
  fraudScore: 'NA',
  trustScore: 'NA',
  payInDetails: {
    qrCode: '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',
    gpayUri: 'gpay://upi/pay?ver=01&mode=15&am=5.00&mam=1.00&cu=INR&pa=npstpay@timecosmos&pn=NPST%20PAY&mc=6012&tr=NPST040120220010&tn=QR%20SIT%20testing&mid=NPSTPAY001&msid=NPSTPAY001-001&mtid=NPSTPAY001-001&category=02&url=http://google.com',
    phonepeUri: 'phonepe://pay?ver=01&mode=15&am=5.00&mam=1.00&cu=INR&pa=npstpay@timecosmos&pn=NPST%20PAY&mc=6012&tr=NPST040120220010&tn=QR%20SIT%20testing&mid=NPSTPAY001&msid=NPSTPAY001-001&mtid=NPSTPAY001-001&category=02&url=http://google.com',
    paytmUri: 'paytmmp://pay?ver=01&mode=15&am=5.00&mam=1.00&cu=INR&pa=npstpay@timecosmos&pn=NPST%20PAY&mc=6012&tr=NPST040120220010&tn=QR%20SIT%20testing&mid=NPSTPAY001&msid=NPSTPAY001-001&mtid=NPSTPAY001-001&category=02&url=http://google.com',
    generatedLink: 'https://staging.decf.in/pay/514o5z3m9z',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  refundAvailability: 'NONE',
  refundableAmount: 10,
  successRedirect: 'https://staging.paysecure.net/getResponse.jsp?success=true',
  failureRedirect: 'https://staging.paysecure.net/getResponse.jsp?success=false',
  cancelRedirect: '',
  successCallback: 'https://staging.paysecure.net',
  failureCallback: 'https://staging.paysecure.net',
  platform: 'API',
  createdFromIp: '103.59.75.113',
  checkoutUrl: 'https://staging.paysecure.net/payments/66c4667bb993c970367c288a/',
  payoutProcess: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

