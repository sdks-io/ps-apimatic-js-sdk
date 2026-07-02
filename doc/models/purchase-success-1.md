
# Purchase Success 1

*This model accepts additional fields of type unknown.*

## Structure

`PurchaseSuccess1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Required | - |
| `client` | [`Client4`](../../doc/models/client-4.md) | Required | - |
| `updatedOn` | `number` | Required | - |
| `type` | `string` | Required | - |
| `paymentMethod` | `string` | Required | - |
| `amountUnit` | `string` | Required | - |
| `errorMsg` | `string` | Required | - |
| `redirectType` | `string` | Required | - |
| `forceRecurring` | `boolean` | Required | - |
| `createdOn` | `number` | Required | - |
| `extraParam` | [`ExtraParam1`](../../doc/models/extra-param-1.md) | Required | - |
| `merchantRef` | `string` | Required | - |
| `merchantName` | `string` | Required | - |
| `purchase` | [`Purchase8`](../../doc/models/purchase-8.md) | Required | - |
| `payment` | [`Payment3`](../../doc/models/payment-3.md) | Required | - |
| `issuerDetails` | [`IssuerDetails`](../../doc/models/issuer-details.md) | Required | - |
| `transactionData` | [`TransactionData6`](../../doc/models/transaction-data-6.md) | Required | - |
| `status` | `string` | Required | - |
| `statusHistory` | [`StatusHistory[]`](../../doc/models/status-history.md) | Required | - |
| `isTest` | `boolean` | Required | - |
| `brandId` | `string` | Required | - |
| `isRecurringToken` | `boolean` | Required | - |
| `referenceGenerated` | `string` | Required | - |
| `issued` | `string` | Required | - |
| `due` | `number` | Required | - |
| `refundUpto` | `number` | Required | - |
| `ccDescriptor` | `string` | Required | - |
| `fraudScore` | `string` | Required | - |
| `trustScore` | `string` | Required | - |
| `payInDetails` | [`PayInDetails3`](../../doc/models/pay-in-details-3.md) | Required | - |
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
import { PurchaseSuccess1 } from 'ps-apimatic-sdk';

const purchaseSuccess1: PurchaseSuccess1 = {
  purchaseId: '6890aba7faa4173bbbbb76c6',
  client: {
    customerId: 'NA',
    email: 'seo2009@test.com',
    phone: '+447755564318',
    fullName: 'Test test',
    dateOfBirth: '1970-07-10',
    streetAddress: '10 New Burlington Street Apt. 214',
    country: 'CA',
    city: 'London',
    zipCode: 'W1S 3BE',
    cc: [],
    bcc: [],
    stateCode: 'QLD',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1754311599,
  type: 'purchase',
  paymentMethod: 'INTERAC-EXPRESS',
  amountUnit: 'MAJOR',
  errorMsg: '',
  redirectType: 'GET',
  forceRecurring: false,
  createdOn: 1754311591,
  extraParam: {
    reference: 'wkdjabf43',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  merchantRef: '6890aba7faa4173bbbbb76c6',
  merchantName: 'arunsinghal',
  purchase: {
    currency: 'CAD',
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
    expireInMin: '1440',
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
    amount: 100,
    currency: 'CAD',
    netAmount: 100,
    feeAmount: 0,
    pendingAmount: 0,
    pendingUnfreezeOn: 'pending_unfreeze_on2',
    description: '',
    paidOn: 1754311592,
    remotePaidOn: 1754311592,
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
      amount: 100,
      maskedPan: 'INTERAC-EXPRESS',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    country: '',
    attempts: [
      {
        clientIp: '103.59.75.176, 104.23.216.90, 18.68.12.74',
        type: 'execute',
        paymentMethod: 'INTERAC-EXPRESS',
        flow: 'payform',
        successful: true,
        country: 'INTERAC-EXPRESS',
        processingTime: 1754311592,
        extra: {
          amount: 100,
          maskedPan: 'INTERAC-EXPRESS',
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
      timestamp: 1754311591,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'pending_execute',
      timestamp: 1754311592,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'payment_in_process',
      timestamp: 1754311599,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  isTest: false,
  brandId: '30f7ce6e-3b7e-46a2-9b50-484fc55be689',
  isRecurringToken: false,
  referenceGenerated: 'PS1060',
  issued: '2025-08-04',
  due: 1754311591,
  refundUpto: 0,
  ccDescriptor: '',
  fraudScore: '0',
  trustScore: '0',
  payInDetails: {
    name: 'INTERAC E-TRANSFER',
    emailAddress: 'fund@ieft.ca',
    referenceNumber: '8g1lya',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  paidOn: 0,
  receivedAmt: 0,
  refundAvailability: 'NONE',
  refundableAmount: 0,
  successRedirect: 'https://your.success.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  cancelRedirect: '',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  platform: 'API',
  createdFromIp: '103.59.75.176, 104.23.216.90, 18.68.12.74',
  checkoutUrl: 'https://api.choicepay.ca/payments/6890aba7faa4173bbbbb76c6/',
  payoutProcess: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

