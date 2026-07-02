
# Purchase Success

*This model accepts additional fields of type unknown.*

## Structure

`PurchaseSuccess`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Required | - |
| `client` | [`Client9`](../../doc/models/client-9.md) | Required | - |
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
| `purchase` | [`Purchase8`](../../doc/models/purchase-8.md) | Required | - |
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
| `payInDetails` | [`PayInDetails`](../../doc/models/pay-in-details.md) | Required | - |
| `paidOn` | `number` | Required | - |
| `receivedAmt` | `number` | Required | - |
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
import { PurchaseSuccess } from 'ps-apimatic-sdk';

const purchaseSuccess: PurchaseSuccess = {
  purchaseId: '67efd0ff97be603f97a3a697',
  client: {
    customerId: 'NA',
    email: 'ashishm.21190@gmail.com',
    phone: '+447755564318',
    fullName: 'Test test',
    dateOfBirth: '1970-07-10',
    streetAddress: '10 New Burlington Street Apt. 214',
    country: 'CA',
    city: 'London',
    zipCode: 'W1S 3BE',
    cc: [],
    bcc: [],
    gender: 'MALE',
    avatarUrl: 'https://res.cloudinary.com/w22/image/upload/v1663783641/photos/currencies/ngn.png',
    stateCode: 'QLD',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1743769856,
  type: 'purchase',
  paymentMethod: 'INTERAC-ETRANSFER',
  amountUnit: 'MAJOR',
  errorMsg: '',
  redirectType: 'GET',
  forceRecurring: false,
  createdOn: 1743769855,
  merchantRef: '67efd0ff97be603f97a3a697',
  merchantName: 'arunsinghal',
  purchase: {
    currency: 'CAD',
    products: [
      {
        name: 'test',
        quantity: 1,
        price: 1,
        discount: 0,
        taxPercent: '0.00',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    total: 1,
    language: 'en',
    notes: '',
    debt: 0,
    totalFormatted: 1,
    expireInMin: '43200',
    taxAmount: 0,
    taxPercent: 0,
    requestClientDetails: [],
    emailMessage: '',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  payment: {
    isOutgoing: false,
    paymentType: 'PURCHASE',
    amount: 1,
    currency: 'CAD',
    netAmount: 1,
    feeAmount: 0,
    pendingAmount: 0,
    pendingUnfreezeOn: 'pending_unfreeze_on2',
    description: '',
    paidOn: 1743769855,
    remotePaidOn: 1743769855,
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
      amount: 1,
      maskedPan: 'INTERAC-ETRANSFER',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    country: '',
    attempts: [
      {
        clientIp: '103.59.75.41, 162.158.88.44, 130.176.93.146',
        type: 'execute',
        paymentMethod: 'INTERAC-ETRANSFER',
        flow: 'payform',
        successful: true,
        country: 'INTERAC-ETRANSFER',
        processingTime: 1743769855,
        extra: {
          amount: 1,
          maskedPan: 'INTERAC-ETRANSFER',
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
      timestamp: 1743769855,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'pending_execute',
      timestamp: 1743769855,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'payment_in_process',
      timestamp: 1743769856,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'viewed',
      timestamp: 1744026697,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  viewedOn: 1744026697,
  isTest: false,
  brandId: '30f7ce6e-3b7e-46a2-9b50-484fc55be689',
  sendReceipt: false,
  isRecurringToken: false,
  skipCapture: false,
  referenceGenerated: 'PS620',
  issued: '2025-04-04',
  due: 1743769855,
  refundUpto: 0,
  ccDescriptor: 'Africhange Technologies',
  fraudScore: 'NA',
  trustScore: 'NA',
  payInDetails: {
    name: 'INTERAC',
    emailAddress: 'transfer@ieft.ca',
    secretQa: '66a8c78af1fc2f768304bce4',
    secretAnswer: 'ps8766a8af',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  paidOn: 0,
  receivedAmt: 0,
  refundAvailability: 'NONE',
  refundableAmount: 0,
  successRedirect: 'https://your.redirect.url/getResponse.jsp?success=true',
  failureRedirect: 'https://your.redirect.url/getResponse.jsp?success=false',
  cancelRedirect: '',
  successCallback: 'https://your.success.callback.url',
  failureCallback: 'https://your.success.failure.url',
  platform: 'API',
  createdFromIp: '103.59.75.41, 162.158.88.44, 130.176.93.146',
  checkoutUrl: 'https://api.choicepay.ca/payments/67efd0ff97be603f97a3a697/',
  payoutProcess: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

