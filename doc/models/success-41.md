
# Success 41

*This model accepts additional fields of type unknown.*

## Structure

`Success41`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Required | - |
| `client` | [`Client104`](../../doc/models/client-104.md) | Required | - |
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
| `transactionData` | [`TransactionData41`](../../doc/models/transaction-data-41.md) | Required | - |
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
| `extraFee` | `string` | Required | - |
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
| `directPostUrl` | `string` | Required | - |
| `payoutProcess` | `boolean` | Required | - |
| `paymentType` | `string` | Required | - |
| `mandateId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success41 } from 'ps-apimatic-sdk';

const success41: Success41 = {
  purchaseId: '6973ad04fa54ee2cf14f438c',
  client: {
    customerId: 'NA',
    email: 'sl68792.bravo@bravapay.com',
    phone: '0557719399',
    fullName: 'Test user',
    dateOfBirth: '2004-07-12',
    streetAddress: '10 New Burlington StreetApt. 214',
    country: 'CA',
    city: 'London',
    zipCode: 'W1S 3BE',
    cc: [],
    bcc: [],
    taxNumber: '+447755564318',
    bankAccountNumber: '1345789678',
    stateCode: 'QLD',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1769188614,
  type: 'purchase',
  paymentMethod: 'VISA',
  amountUnit: 'MAJOR',
  errorMsg: 'ERROR_PARSING_GROUP_ID',
  errorCode: 'NA',
  forceRecurring: false,
  createdOn: 1769188612,
  merchantRef: '6973ad04fa54ee2cf14f438c',
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'gaming cards',
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
    requestAmount: 10,
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
    legalName: 'zenith',
    brandName: 'zenith',
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
      expiryMonth: '01',
      amount: 10,
      cardIssuer: 'VISION BANK',
      maskedPan: '42222222*2222',
      cardBrand: 'VISA',
      cardIssuerCountry: 'SA',
      cardType: 'DEBIT',
      cardholderName: 'fgjhknms',
      expiryYear: '29',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    country: '',
    attempts: [
      {
        clientIp: '49.36.232.107',
        type: 'execute',
        paymentMethod: 'VISA',
        flow: 'payform',
        successful: false,
        country: 'VISA',
        processingTime: 1769188612,
        extra: {
          amount: 10,
          maskedPan: 'VISA',
          cardBrand: 'VISA',
          cardIssuerCountry: 'VISA',
          cardholderName: 'Test user',
          expiryMonth: 'expiry_month6',
          cardIssuer: 'card_issuer2',
          cardType: 'card_type8',
          expiryYear: 'expiry_year4',
          additionalProperties: {
            'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
          },
        },
        error: {
          message: 'This customer can not be processed !',
          code: 'transaction_error',
          additionalProperties: {
            'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
          },
        },
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      {
        clientIp: '',
        type: 'execute',
        paymentMethod: 'VISA',
        flow: 'payform',
        successful: false,
        country: 'SA',
        processingTime: 1769188613,
        extra: {
          amount: 10,
          maskedPan: '42222222*2222',
          cardBrand: 'VISA',
          cardIssuerCountry: 'SA',
          cardholderName: 'fgjhknms',
          expiryMonth: '01',
          cardIssuer: 'VISION BANK',
          cardType: 'DEBIT',
          expiryYear: '29',
          additionalProperties: {
            'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
          },
        },
        error: {
          message: 'ERROR_PARSING_GROUP_ID',
          code: 'transaction_error',
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
  status: 'ERROR',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1769188612,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'pending_execute',
      timestamp: 1769188612,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'error',
      timestamp: 1769188613,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'pending_execute',
      timestamp: 1769188613,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'error',
      timestamp: 1769188614,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'viewed',
      timestamp: 1770016552,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  viewedOn: 1770016552,
  isTest: false,
  brandId: '555c458b-e737-4905-adb2-2451d37cbb6e',
  sendReceipt: false,
  isRecurringToken: false,
  skipCapture: false,
  referenceGenerated: 'PS1841',
  issued: '2026-01-23',
  due: 1769188612,
  refundUpto: 0,
  ccDescriptor: '',
  fraudScore: 'NA',
  trustScore: 'NA',
  extraFee: '0',
  paidOn: 0,
  receivedAmt: 0,
  taxAmount: 0,
  surcharge: 0,
  surchargeType: '',
  sessionId: '',
  refundAvailability: 'NONE',
  refundableAmount: 0,
  successRedirect: 'https://staging.paysecure.net/getResponse.jsp?issucces=true',
  failureRedirect: 'https://staging.paysecure.net/getResponse.jsp?issucces=false',
  pendingRedirect: 'https://staging.paysecure.net/getResponse.jsp?issucces=pending ',
  cancelRedirect: '',
  successCallback: 'https://www.google.com/',
  failureCallback: 'https://staging.paysecure.net/merchant',
  platform: 'API',
  createdFromIp: '49.36.232.107',
  checkoutUrl: 'https://test4.paymentsclub.net/payments/a28ed9974a22a4cbd5f2f49cc26cc334/',
  directPostUrl: 'https://test4.paymentsclub.net/api/v1/p/6973ad04fa54ee2cf14f438c/',
  payoutProcess: false,
  paymentType: 'internal recurring',
  mandateId: '696bc39a7bc779fac5201357',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

