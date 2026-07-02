
# Success 13

*This model accepts additional fields of type unknown.*

## Structure

`Success13`

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
| `payoutProcess` | `boolean` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success13 } from 'ps-apimatic-sdk';

const success13: Success13 = {
  purchaseId: '69ec68f9f76f0f58bd700058',
  client: {
    customerId: 'NA',
    email: 'agarapex@gmail.com',
    phone: '243995980380',
    fullName: 'Rahul Agarwal',
    dateOfBirth: '1994-31-04',
    streetAddress: '10 New Burlington StreetApt. 214',
    country: 'CD',
    city: 'Jaipur',
    zipCode: 'W1S 3BE',
    cc: [],
    bcc: [],
    stateCode: 'RJ',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1777101049,
  type: 'purchase',
  paymentMethod: 'MOBILEMONEY',
  amountUnit: 'MAJOR',
  errorMsg: '',
  errorCode: 'NA',
  forceRecurring: false,
  createdOn: 1777101049,
  merchantRef: '69ec68f9f76f0f58bd700058',
  purchase: {
    currency: 'CDF',
    products: [
      {
        name: 'gaming cards',
        quantity: 1,
        price: 1000,
        discount: 0,
        taxPercent: '0.00',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    total: 1000,
    requestAmount: 1000,
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
      timestamp: 1777101049,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  isTest: false,
  brandId: '59c5ed48-caf9-464a-ba54-26e1e02bc1bc',
  sendReceipt: false,
  isRecurringToken: false,
  skipCapture: false,
  referenceGenerated: 'PS1711',
  issued: '2026-04-25',
  due: 1777101049,
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
  successRedirect: 'https://google.com/',
  failureRedirect: 'https://paysecure.net',
  pendingRedirect: 'https://facebook.com',
  cancelRedirect: '',
  successCallback: 'https://staging.paysecure.net/merchant',
  failureCallback: 'https://staging.paysecure.net/merchant',
  platform: 'API',
  createdFromIp: '2406:b400:75:584c:8889:bfe5:9552:8720',
  checkoutUrl: 'https://api.choicepay.ca/payments/5f95c39387eefc684560013794f41455/',
  payoutProcess: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

