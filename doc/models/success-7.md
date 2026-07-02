
# Success 7

*This model accepts additional fields of type unknown.*

## Structure

`Success7`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Required | - |
| `client` | [`Client26`](../../doc/models/client-26.md) | Required | - |
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
| `purchase` | [`Purchase17`](../../doc/models/purchase-17.md) | Required | - |
| `issuerDetails` | [`IssuerDetails11`](../../doc/models/issuer-details-11.md) | Required | - |
| `transactionData` | `unknown` | Required | - |
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
| `pendingRedirect` | `string` | Required | - |
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
import { Success7 } from 'ps-apimatic-sdk';

const success7: Success7 = {
  purchaseId: '65f9368cb905381ba207b3c4',
  client: {
    email: 'test@gmail.com',
    fullName: 'Test test',
    taxNumber: '39933551809',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1710831244,
  type: 'purchase',
  paymentMethod: 'PIX',
  amountUnit: 'MAJOR',
  errorMsg: '',
  redirectType: 'POST',
  forceRecurring: false,
  createdOn: 1710831244,
  merchantRef: '65f9368cb905381ba207b3c4',
  merchantName: 'test',
  purchase: {
    currency: 'USD',
    products: [
      {
        price: 10,
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    total: 10,
    language: 'en',
    totalFormatted: 1,
    timezone: 'MIT',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  issuerDetails: {
    bankAccounts: [
      {
        bankAccount: '',
        bankCode: '',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    legalName: 'newbrand',
    brandName: 'newbrand',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  transactionData: {  },
  status: 'CREATED',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1710831244,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  isTest: false,
  brandId: '90ed108b-6753-465d-8a21-e2cc604ff814',
  sendReceipt: false,
  isRecurringToken: false,
  skipCapture: false,
  referenceGenerated: 'PS2696',
  issued: '2024-03-19',
  due: 1710831244,
  refundUpto: 0,
  ccDescriptor: '',
  fraudScore: 'NA',
  trustScore: 'NA',
  refundAvailability: 'NONE',
  refundableAmount: 0,
  successRedirect: 'https://test.com/getResponse.jsp?success=true',
  pendingRedirect: 'https://test.com/getResponse.jsp?success=pending',
  failureRedirect: 'https://test.com/getResponse.jsp?success=false',
  cancelRedirect: '',
  successCallback: 'https://test1.com',
  failureCallback: 'https://test2.com',
  platform: 'API',
  createdFromIp: '223.182.100.34',
  checkoutUrl: 'https://api.paysecure.net/payments/65f9368cb905381ba207b3c4/',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

