
# Purchases Success 2

*This model accepts additional fields of type unknown.*

## Structure

`PurchasesSuccess2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Required | - |
| `client` | [`Client35`](../../doc/models/client-35.md) | Required | - |
| `updatedOn` | `number` | Required | - |
| `type` | `string` | Required | - |
| `paymentMethod` | `string` | Required | - |
| `amountUnit` | `string` | Required | - |
| `errorMsg` | `string` | Required | - |
| `redirectType` | `string` | Required | - |
| `forceRecurring` | `boolean` | Required | - |
| `createdOn` | `number` | Required | - |
| `merchantRef` | `string` | Required | - |
| `instruction` | `string` | Required | - |
| `merchantName` | `string` | Required | - |
| `purchase` | [`Purchase21`](../../doc/models/purchase-21.md) | Required | - |
| `payment` | [`Payment3`](../../doc/models/payment-3.md) | Required | - |
| `issuerDetails` | [`IssuerDetails`](../../doc/models/issuer-details.md) | Required | - |
| `transactionData` | [`TransactionData6`](../../doc/models/transaction-data-6.md) | Required | - |
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
| `payInDetails` | [`PayInDetails4`](../../doc/models/pay-in-details-4.md) | Required | - |
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
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PurchasesSuccess2 } from 'ps-apimatic-sdk';

const purchasesSuccess2: PurchasesSuccess2 = {
  purchaseId: '667cfc59f0bd8d672c8fc6c8',
  client: {
    email: 'deepakdeepaksinghal@gmail.com',
    phone: '+447755564318',
    fullName: 'Test test',
    dateOfBirth: '1970-07-10',
    streetAddress: '10 New Burlington Street Apt. 214',
    country: 'EG',
    city: 'London',
    zipCode: 'W1S 3BE',
    cc: [],
    bcc: [],
    stateCode: 'QLD',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1719467097,
  type: 'purchase',
  paymentMethod: 'FAWRYPAY',
  amountUnit: 'MAJOR',
  errorMsg: '',
  redirectType: 'POST',
  forceRecurring: false,
  createdOn: 1719467097,
  merchantRef: '667cfc59f0bd8d672c8fc6c8',
  instruction: 'Please use the reference number 9350717665 to pay 10 EGP for this order at Fawrypay store. Complete the payment before 6/29/2024 5:45:00 AM +00:00',
  merchantName: 'merchant002',
  purchase: {
    currency: 'EGP',
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
    currency: 'EGP',
    netAmount: 10,
    feeAmount: 0,
    pendingAmount: 0,
    pendingUnfreezeOn: 'pending_unfreeze_on2',
    description: '',
    paidOn: 1719467097,
    remotePaidOn: 1719467097,
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
      maskedPan: 'FAWRYPAY',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    country: '',
    attempts: [
      {
        clientIp: '110.235.229.106',
        type: 'execute',
        paymentMethod: 'FAWRYPAY',
        flow: 'payform',
        successful: true,
        country: 'FAWRYPAY',
        processingTime: 1719467097,
        extra: {
          amount: 10,
          maskedPan: 'FAWRYPAY',
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
      timestamp: 1719467097,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'pending_execute',
      timestamp: 1719467097,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'payment_in_process',
      timestamp: 1719467097,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'viewed',
      timestamp: 1719467160,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  viewedOn: 1719467160,
  isTest: false,
  brandId: 'c4003b2c-22d4-4dc1-ad0c-c6b54f8c9636',
  sendReceipt: false,
  isRecurringToken: false,
  skipCapture: false,
  referenceGenerated: 'PS10253',
  issued: '2024-06-27',
  due: 1719467097,
  refundUpto: 1735015500,
  ccDescriptor: '',
  fraudScore: 'NA',
  trustScore: 'NA',
  payInDetails: {
    referenceNumber: '9350717665',
    paymentMethod: 'PAYATFAWRY',
    transactionExpiry: '29 Jun 2024 05:45:00:245 +0000',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  refundAvailability: 'NONE',
  refundableAmount: 10,
  successRedirect: 'https://your.success.redirect.com/getResponse.jsp?success=true',
  failureRedirect: 'https://your.failure.redirect.com/getResponse.jsp?success=false',
  cancelRedirect: '',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  platform: 'API',
  createdFromIp: '110.235.229.106',
  checkoutUrl: 'https://api.paysecure.net/payments/667cfb2cf0bd8d672c8fc562/',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

