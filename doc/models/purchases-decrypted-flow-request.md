
# Purchases Decrypted Flow Request

*This model accepts additional fields of type unknown.*

## Structure

`PurchasesDecryptedFlowRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client52`](../../doc/models/client-52.md) | Required | - |
| `purchase` | [`Purchase`](../../doc/models/purchase.md) | Required | - |
| `paymentMethod` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `extraParam` | [`ExtraParam3`](../../doc/models/extra-param-3.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PurchasesDecryptedFlowRequest } from 'ps-apimatic-sdk';

const purchasesDecryptedFlowRequest: PurchasesDecryptedFlowRequest = {
  client: {
    customerId: 'NA',
    email: 'himanshu1@paysecure.net',
    fullName: 'OpHM',
    dateOfBirth: '1800-01-01',
    streetAddress: 'SB-124',
    country: 'BR',
    city: 'DLJPR',
    zipCode: '110001',
    cc: [],
    bcc: [],
    stateCode: 'DL',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    currency: 'EUR',
    products: [
      {
        name: 'e-commerce',
        price: '10',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  paymentMethod: 'GOOGLEPAY',
  brandId: 'f1764688-d991-481b-be63-9ee7f33dcd31',
  successRedirect: 'https://google.com/',
  pendingRedirect: 'https://paysecure.net',
  failureRedirect: 'https://facebook.com/',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  extraParam: {
    googlepayParam: {
      googleMerchantId: 'merchant:1234567890',
      googlepayDecryptedPayload: {
        messageExpiration: '1735689600000',
        messageId: 'AH2EjtfkYz...',
        paymentMethod: 'CARD',
        paymentMethodDetails: {
          pan: '4111111111111111',
          expirationMonth: 12,
          expirationYear: 2027,
          authMethod: 'CRYPTOGRAM_3DS',
          cryptogram: 'AgAAAAAABk4D...',
          eciIndicator: '05',
          additionalProperties: {
            'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
          },
        },
        gatewayMerchantId: 'your_gateway_merchant_id',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

