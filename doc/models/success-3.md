
# Success 3

*This model accepts additional fields of type unknown.*

## Structure

`Success3`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Required | - |
| `client` | [`Client15`](../../doc/models/client-15.md) | Required | - |
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
import { Success3 } from 'ps-apimatic-sdk';

const success3: Success3 = {
  purchaseId: '670cb0affcc7f4706acb65e0',
  client: {
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
  updatedOn: 1728884911,
  type: 'purchase',
  paymentMethod: 'INTERAC-REQUEST-MONEY',
  amountUnit: 'MAJOR',
  errorMsg: '',
  redirectType: 'POST',
  forceRecurring: false,
  createdOn: 1728884911,
  merchantRef: '670cb0affcc7f4706acb65e0',
  merchantName: 'ajay03',
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
    expireInMin: '1440',
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
    paidOn: 1728884911,
    remotePaidOn: 1728884911,
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
    legalName: 'r4',
    brandName: 'r4',
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
      maskedPan: 'INTERAC-DEBIT',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    country: '',
    attempts: [
      {
        clientIp: '110.235.229.9',
        type: 'execute',
        paymentMethod: 'INTERAC-DEBIT',
        flow: 'payform',
        successful: true,
        country: 'INTERAC-DEBIT',
        processingTime: 1728884911,
        extra: {
          amount: 1,
          maskedPan: 'INTERAC-DEBIT',
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
      timestamp: 1728884911,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'pending_execute',
      timestamp: 1728884911,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'payment_in_process',
      timestamp: 1728884911,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  isTest: false,
  brandId: '0cea7af3-23b2-4278-ab94-acf4076cbee4',
  sendReceipt: false,
  isRecurringToken: false,
  skipCapture: false,
  referenceGenerated: 'PS3',
  issued: '2024-10-14',
  due: 1728884911,
  refundUpto: 1744433315,
  ccDescriptor: '',
  fraudScore: 'NA',
  trustScore: 'NA',
  refundAvailability: 'NONE',
  refundableAmount: 1,
  successRedirect: 'https://your.redirect.url/getResponse.jsp?success=true',
  failureRedirect: 'https://your.redirect.url/getResponse.jsp?success=false',
  cancelRedirect: '',
  successCallback: 'https://your.success.callback.url',
  failureCallback: 'https://your.success.failure.url',
  platform: 'API',
  createdFromIp: '110.235.229.9',
  checkoutUrl: 'https://api.paysecure.net/payments/670cb0affcc7f4706acb65e0/',
  payoutProcess: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

