
# Purchases Success 1

*This model accepts additional fields of type unknown.*

## Structure

`PurchasesSuccess1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Required | - |
| `client` | [`Client10`](../../doc/models/client-10.md) | Required | - |
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
| `purchase` | [`Purchase9`](../../doc/models/purchase-9.md) | Required | - |
| `payment` | [`Payment4`](../../doc/models/payment-4.md) | Required | - |
| `issuerDetails` | [`IssuerDetails`](../../doc/models/issuer-details.md) | Required | - |
| `transactionData` | [`TransactionData7`](../../doc/models/transaction-data-7.md) | Required | - |
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
import { PurchasesSuccess1 } from 'ps-apimatic-sdk';

const purchasesSuccess1: PurchasesSuccess1 = {
  purchaseId: '6790e75fa46a5a5bb0b00e55',
  client: {
    customerId: 'NA',
    email: 'ashishm.21190@gmail.com',
    phone: '+14377717874',
    fullName: 'Test test',
    dateOfBirth: '1970-07-10',
    streetAddress: '10 New Burlington Street Apt. 214',
    country: 'CA',
    city: 'London',
    zipCode: 'W1S 3BE',
    cc: [],
    bcc: [],
    gender: 'MALE',
    stateCode: 'QLD',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1737549752,
  type: 'purchase',
  paymentMethod: 'INTERAC-ETRANSFER',
  amountUnit: 'MAJOR',
  errorMsg: 'Transaction succeeded-APPROVED',
  redirectType: 'GET',
  forceRecurring: false,
  createdOn: 1737549663,
  merchantRef: '6790e75fa46a5a5bb0b00e55',
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
    total: 2,
    language: 'en',
    notes: '',
    debt: 0,
    totalFormatted: 1,
    expireInMin: '43200',
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
    paidOn: 1737549663,
    remotePaidOn: 1737549663,
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
        clientIp: '103.59.75.42, 172.71.186.102, 130.176.183.14',
        type: 'execute',
        paymentMethod: 'INTERAC-ETRANSFER',
        flow: 'payform',
        successful: true,
        country: 'INTERAC',
        processingTime: 1737549663,
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
  status: 'PAID',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1737549663,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'pending_execute',
      timestamp: 1737549663,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'payment_in_process',
      timestamp: 1737549664,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'paid 2.0',
      timestamp: 1737549752,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'viewed',
      timestamp: 1737549750,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  viewedOn: 1738749942,
  isTest: false,
  brandId: '30f7ce6e-3b7e-46a2-9b50-484fc55be689',
  sendReceipt: false,
  isRecurringToken: false,
  skipCapture: false,
  referenceGenerated: 'PS376',
  issued: '2025-01-22',
  due: 1737549663,
  refundUpto: 0,
  ccDescriptor: 'Africhange Technologies',
  fraudScore: 'NA',
  trustScore: 'NA',
  payInDetails: {
    name: 'INTERAC',
    emailAddress: 'deposit@ieft.ca',
    secretQa: '66a8c78af1fc2f768304bce4',
    secretAnswer: 'ps8766a8af',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  paidOn: 1737549752,
  receivedAmt: 2,
  refundAvailability: 'NONE',
  refundableAmount: 0,
  successRedirect: 'https://your.redirect.url/getResponse.jsp?success=true',
  failureRedirect: 'https://your.redirect.url/getResponse.jsp?success=false',
  cancelRedirect: '',
  successCallback: 'https://webhook.site/83df9776-3590-4e25-9222-870e931ac868',
  failureCallback: 'https://webhook.site/83df9776-3590-4e25-9222-870e931ac868',
  platform: 'API',
  createdFromIp: '103.59.75.42, 172.71.186.102, 130.176.183.14',
  checkoutUrl: 'https://api.choicepay.ca/payments/6790e75fa46a5a5bb0b00e55/',
  payoutProcess: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

