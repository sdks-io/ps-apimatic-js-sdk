
# Purchases Encrypted Flow Request

*This model accepts additional fields of type unknown.*

## Structure

`PurchasesEncryptedFlowRequest`

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
| `extraParam` | [`ExtraParam2`](../../doc/models/extra-param-2.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PurchasesEncryptedFlowRequest } from 'ps-apimatic-sdk';

const purchasesEncryptedFlowRequest: PurchasesEncryptedFlowRequest = {
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
      googlepayEncryptedPayload: '{"signature":"MEUCIQC...","intermediateSigningKey":{...},"protocolVersion":"ECv2","signedMessage":"{...}"}',
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

