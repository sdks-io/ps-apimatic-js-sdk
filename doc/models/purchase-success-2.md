
# Purchase Success 2

*This model accepts additional fields of type unknown.*

## Structure

`PurchaseSuccess2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Required | - |
| `client` | [`Client24`](../../doc/models/client-24.md) | Required | - |
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
| `purchase` | [`Purchase16`](../../doc/models/purchase-16.md) | Required | - |
| `issuerDetails` | [`IssuerDetails11`](../../doc/models/issuer-details-11.md) | Required | - |
| `transactionData` | `unknown` | Required | - |
| `status` | `string` | Required | - |
| `statusHistory` | [`StatusHistory[]`](../../doc/models/status-history.md) | Required | - |
| `pixPayload` | [`PixPayload`](../../doc/models/pix-payload.md) | Required | - |
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
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `platform` | `string` | Required | - |
| `createdFromIp` | `string` | Required | - |
| `checkoutUrl` | `string` | Required | - |
| `payoutProcess` | `boolean` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PurchaseSuccess2 } from 'ps-apimatic-sdk';

const purchaseSuccess2: PurchaseSuccess2 = {
  purchaseId: '65f9368cb905381ba207b3c4',
  client: {
    email: 'test@gmail.com',
    fullName: 'test test',
    country: 'BR',
    city: 'Brasília',
    stateCode: 'SP',
    streetAddress: 'Praça da Bíblia 1308',
    zipCode: '57312-140',
    dateOfBirth: '1994-31-04',
    phone: '+558262362732',
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
      timestamp: 1764922723,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'pending_execute',
      timestamp: 1764922723,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'payment_in_process',
      timestamp: 1764922727,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  pixPayload: {
    payload: '00020101021226800014br.gov.bcb.pix2558pix.asaas.com/qr/cobv/e3eb36eb-7e9b-404d-9bd3-b486a42da3445204000053039865802BR5925A55 CONSULTORIA EM CREDIT6009Sao Paulo61080455202062070503***630451CA',
    qrCode: 'iVBORw0KGgoAAAANSUhEUgAAAZ8AAAGfCAIAAAAPgEjDAAAP4UlEQVR42u3bUY7cSA4EUN … ..',
    expirationDate: '2025-03-27 23:59:59',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
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
  successCallback: 'https://test1.com',
  failureCallback: 'https://test2.com',
  platform: 'API',
  createdFromIp: '183.83.53.0',
  checkoutUrl: 'https://api.choicepay.ca/payments/33ddc21c6073a7ac722288f0b2ec35be/',
  payoutProcess: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

