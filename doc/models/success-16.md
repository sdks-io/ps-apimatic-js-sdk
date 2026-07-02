
# Success 16

*This model accepts additional fields of type unknown.*

## Structure

`Success16`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Required | - |
| `client` | [`Client66`](../../doc/models/client-66.md) | Required | - |
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
| `purchase` | [`Purchase45`](../../doc/models/purchase-45.md) | Required | - |
| `payment` | [`Payment4`](../../doc/models/payment-4.md) | Required | - |
| `issuerDetails` | [`IssuerDetails`](../../doc/models/issuer-details.md) | Required | - |
| `transactionData` | [`TransactionData7`](../../doc/models/transaction-data-7.md) | Required | - |
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
| `paidOn` | `number` | Required | - |
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
import { Success16 } from 'ps-apimatic-sdk';

const success16: Success16 = {
  purchaseId: '683d6bab12b471481d4f66cf',
  client: {
    customerId: 'NA',
    email: 'example22@paysecure.net',
    phone: '9999999999',
    dateOfBirth: '1800-01-01',
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
  updatedOn: 1748855724,
  type: 'purchase',
  paymentMethod: 'NEOSURF',
  amountUnit: 'MAJOR',
  errorMsg: '',
  redirectType: 'GET',
  forceRecurring: false,
  createdOn: 1748855723,
  merchantRef: '683d6bab12b471481d4f66cf',
  merchantName: 'arunsinghal',
  purchase: {
    currency: 'AUD',
    products: [
      {
        name: 'dk',
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
    currency: 'AUD',
    netAmount: 1,
    feeAmount: 0,
    pendingAmount: 0,
    pendingUnfreezeOn: 'pending_unfreeze_on2',
    description: '',
    paidOn: 1748855723,
    remotePaidOn: 1748855723,
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
      maskedPan: 'NEOSURF',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    country: '',
    attempts: [
      {
        clientIp: '103.59.75.242, 162.158.23.126, 130.176.183.12',
        type: 'execute',
        paymentMethod: 'NEOSURF',
        flow: 'payform',
        successful: true,
        country: 'NEOSURF',
        processingTime: 1748855723,
        extra: {
          amount: 1,
          maskedPan: 'NEOSURF',
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
      timestamp: 1748855723,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'pending_execute',
      timestamp: 1748855723,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'payment_in_process',
      timestamp: 1748855724,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  isTest: false,
  brandId: '30f7ce6e-3b7e-46a2-9b50-484fc55be689',
  isRecurringToken: false,
  referenceGenerated: 'PS784',
  issued: '2025-06-02',
  due: 1748855723,
  refundUpto: 1749024924,
  ccDescriptor: '',
  fraudScore: '0',
  trustScore: '0',
  paidOn: 0,
  refundAvailability: 'NONE',
  refundableAmount: 1,
  successRedirect: 'https://your.success.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  cancelRedirect: '',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  platform: 'API',
  createdFromIp: '103.59.75.242, 162.158.23.126, 130.176.183.12',
  checkoutUrl: 'https://api.choicepay.ca/payments/683d6bab12b471481d4f66cf/',
  payoutProcess: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

