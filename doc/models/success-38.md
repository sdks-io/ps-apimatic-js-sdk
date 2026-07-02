
# Success 38

*This model accepts additional fields of type unknown.*

## Structure

`Success38`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Required | - |
| `client` | [`Client103`](../../doc/models/client-103.md) | Required | - |
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
| `payment` | [`Payment3`](../../doc/models/payment-3.md) | Required | - |
| `issuerDetails` | [`IssuerDetails`](../../doc/models/issuer-details.md) | Required | - |
| `transactionData` | [`TransactionData40`](../../doc/models/transaction-data-40.md) | Required | - |
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
import { Success38 } from 'ps-apimatic-sdk';

const success38: Success38 = {
  purchaseId: '69f8d407ea26ad15715ebb85',
  client: {
    customerId: 'NA',
    email: 'recurring@yopmail.com',
    dateOfBirth: '1800-01-01',
    streetAddress: '120, jaipur',
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
  updatedOn: 1777914890,
  type: 'purchase',
  paymentMethod: 'VISA',
  amountUnit: 'MAJOR',
  errorMsg: '',
  errorCode: 'NA',
  forceRecurring: false,
  createdOn: 1777914887,
  merchantRef: '69f8d407ea26ad15715ebb85',
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'gaming cards',
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
    requestAmount: 1,
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
    currency: 'USD',
    netAmount: 1,
    feeAmount: 0,
    pendingAmount: 0,
    pendingUnfreezeOn: 'pending_unfreeze_on2',
    description: '',
    paidOn: 1777914887,
    remotePaidOn: 1777914887,
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
    extra: {
      expiryMonth: '04',
      amount: 1,
      cardIssuer: 'REVOLUT BANK UAB',
      maskedPan: '41659827****0724',
      cardBrand: 'VISA',
      cardIssuerCountry: 'CH',
      cardType: 'DEBIT',
      cardholderName: 'Amit Hooja',
      expiryYear: '31',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    country: '',
    attempts: [
      {
        clientIp: '183.82.186.156',
        type: 'execute',
        paymentMethod: 'VISA',
        flow: 'payform',
        successful: true,
        country: 'CH',
        processingTime: 1777914887,
        extra: {
          expiryMonth: '04',
          amount: 1,
          cardIssuer: 'REVOLUT BANK UAB',
          maskedPan: '41659827****0724',
          cardBrand: 'VISA',
          cardIssuerCountry: 'CH',
          cardType: 'DEBIT',
          cardholderName: 'Amit Hooja',
          expiryYear: '31',
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
      timestamp: 1777914887,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'pending_execute',
      timestamp: 1777914887,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'paid',
      timestamp: 1777914890,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  isTest: false,
  brandId: 'brand_id',
  sendReceipt: false,
  isRecurringToken: false,
  skipCapture: false,
  referenceGenerated: 'PS1738',
  issued: '2026-05-04',
  due: 1777914887,
  refundUpto: 1780503290,
  ccDescriptor: 'multitasklist',
  fraudScore: '0',
  trustScore: '0',
  extraFee: '0',
  totalRefunded: 0,
  paidOn: 1777914890,
  receivedAmt: 0,
  taxAmount: 0,
  surcharge: 0,
  surchargeType: '',
  sessionId: '',
  refundAvailability: 'NONE',
  refundableAmount: 1,
  successRedirect: 'https://staging.paysecure.net/getResponse.jsp?issucces=true',
  failureRedirect: 'https://staging.paysecure.net/getResponse.jsp?issucces=false',
  cancelRedirect: '',
  successCallback: '',
  failureCallback: 'https://staging.paysecure.net/merchant',
  platform: 'API',
  createdFromIp: '2406:b400:75:22bd:b48e:a33e:4e26:a542',
  checkoutUrl: 'https://api.choicepay.ca/payments/0bc9c18600980b03a08fb030726428f8/',
  directPostUrl: 'https://api.choicepay.ca/api/v1/p/69f8d407ea26ad15715ebb85/',
  payoutProcess: false,
  paymentType: 'recurring',
  mandateId: '69f8cfa1db7ca561ab23fed2',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

