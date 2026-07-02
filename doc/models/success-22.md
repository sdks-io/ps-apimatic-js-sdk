
# Success 22

*This model accepts additional fields of type unknown.*

## Structure

`Success22`

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
| `purchase` | [`Purchase24`](../../doc/models/purchase-24.md) | Required | - |
| `payment` | [`Payment3`](../../doc/models/payment-3.md) | Required | - |
| `issuerDetails` | [`IssuerDetails`](../../doc/models/issuer-details.md) | Required | - |
| `transactionData` | [`TransactionData6`](../../doc/models/transaction-data-6.md) | Required | - |
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
import { Success22 } from 'ps-apimatic-sdk';

const success22: Success22 = {
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
  paymentMethod: 'BANKTRANSFER',
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
      maskedPan: 'BANKTRANSFER',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    country: '',
    attempts: [
      {
        clientIp: '103.59.75.113',
        type: 'execute',
        paymentMethod: 'BANKTRANSFER',
        flow: 'payform',
        successful: true,
        country: 'BANKTRANSFER',
        processingTime: 1724147324,
        extra: {
          amount: 10,
          maskedPan: 'BANKTRANSFER',
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
    },
    {
      status: 'paid',
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

