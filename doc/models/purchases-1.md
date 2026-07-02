
# Purchases 1

*This model accepts additional fields of type unknown.*

## Structure

`Purchases1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Required | - |
| `client` | [`Client75`](../../doc/models/client-75.md) | Required | - |
| `updatedOn` | `number` | Required | - |
| `type` | `string` | Required | - |
| `paymentMethod` | `string` | Required | - |
| `amountUnit` | `string` | Required | - |
| `errorMsg` | `string` | Required | - |
| `redirectType` | `string` | Required | - |
| `forceRecurring` | `boolean` | Required | - |
| `createdOn` | `number` | Required | - |
| `extraParam` | [`ExtraParam9`](../../doc/models/extra-param-9.md) | Required | - |
| `merchantRef` | `string` | Required | - |
| `merchantName` | `string` | Required | - |
| `purchase` | [`Purchase49`](../../doc/models/purchase-49.md) | Required | - |
| `payment` | [`Payment17`](../../doc/models/payment-17.md) | Required | - |
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
import { Purchases1 } from 'ps-apimatic-sdk';

const purchases1: Purchases1 = {
  purchaseId: '6874ce9402f0f25ed8fc66a7',
  client: {
    customerId: 'NA',
    email: 'gaurav@gmail.com',
    phone: '9999999999',
    fullName: 'Test test',
    dateOfBirth: '1800-01-01',
    streetAddress: 'test test',
    country: 'US',
    city: '123',
    zipCode: '234567',
    cc: [],
    bcc: [],
    taxNumber: '39933551809',
    stateCode: 'NYC',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1752485524,
  type: 'purchase',
  paymentMethod: 'CRYPTO-BRIDGE',
  amountUnit: 'MAJOR',
  errorMsg: '',
  redirectType: 'GET',
  forceRecurring: false,
  createdOn: 1752485524,
  extraParam: {
    clientFee: 0.1,
    toAddress: [
      {
        symbol: 'ETH',
        network: 'ETHEREUM',
        address: '0xc4db7bBB898B98D15be823454d1dff6C308BC9A4',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      {
        symbol: 'USDC',
        network: 'POLYGON',
        address: '0xc4cs7bBB898B89D15be823445d1dff6C380BC9D3',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  merchantRef: '6874ce9402f0f25ed8fc66a7',
  merchantName: 'test',
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'product name',
        quantity: 1,
        price: 5.86,
        discount: 0,
        taxPercent: '0.00',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    total: 5.86,
    language: 'en',
    notes: '',
    debt: 0,
    totalFormatted: 1,
    taxAmount: 0,
    taxPercent: 0,
    requestClientDetails: [],
    timezone: 'Asia/Hong_Kong',
    emailMessage: '',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  payment: {
    isOutgoing: false,
    paymentType: 'PURCHASE',
    amount: 5.86,
    currency: 'USD',
    netAmount: 5.86,
    feeAmount: 0,
    pendingAmount: 0,
    pendingUnfreezeOn: 'pending_unfreeze_on2',
    description: '',
    paidOn: 1752485524,
    remotePaidOn: 1752485524,
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
    legalName: 'iUnicharge',
    brandName: 'iUnicharge',
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
      amount: 5.86,
      maskedPan: 'CRYPTO-BRIDGE',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    country: '',
    attempts: [
      {
        clientIp: '103.59.75.157, 172.69.203.75, 18.68.12.102',
        type: 'execute',
        paymentMethod: 'CRYPTO-BRIDGE',
        flow: 'payform',
        successful: true,
        country: 'CRYPTO-BRIDGE',
        processingTime: 1752485524,
        extra: {
          amount: 5.86,
          maskedPan: 'CRYPTO-BRIDGE',
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
      timestamp: 1752485524,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'pending_execute',
      timestamp: 1752485524,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'payment_in_process',
      timestamp: 1752485524,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  isTest: false,
  brandId: 'cec67fe3-a01d-4d0d-b100-9fafb200fe15',
  sendReceipt: false,
  isRecurringToken: false,
  skipCapture: false,
  referenceGenerated: 'PS1682',
  issued: '2025-07-14',
  due: 1752485524,
  refundUpto: 0,
  ccDescriptor: '',
  fraudScore: '100',
  trustScore: '2',
  paidOn: 0,
  refundAvailability: 'NONE',
  refundableAmount: 0,
  successRedirect: 'https://your.success.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  cancelRedirect: '',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  platform: 'API',
  createdFromIp: '103.59.75.157, 172.69.203.75, 18.68.12.102',
  checkoutUrl: 'https://api.choicepay.ca/payments/6874ce9402f0f25ed8fc66a7/',
  payoutProcess: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

