
# Purchases Decrypted Flow Request 1

*This model accepts additional fields of type unknown.*

## Structure

`PurchasesDecryptedFlowRequest1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client57`](../../doc/models/client-57.md) | Required | - |
| `purchase` | [`Purchase`](../../doc/models/purchase.md) | Required | - |
| `paymentMethod` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `extraParam` | [`ExtraParam5`](../../doc/models/extra-param-5.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PurchasesDecryptedFlowRequest1 } from 'ps-apimatic-sdk';

const purchasesDecryptedFlowRequest1: PurchasesDecryptedFlowRequest1 = {
  client: {
    email: 'customer@example.com',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'Product',
        price: '10.00',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  paymentMethod: 'APPLEPAY',
  brandId: 'your_brand_id',
  successRedirect: 'https://success.com',
  pendingRedirect: 'https://pending.com',
  failureRedirect: 'https://failure.com',
  extraParam: {
    applepayParam: {
      applepayDecryptedPayload: {
        applicationPrimaryAccountNumber: '4111111111111111',
        applicationExpirationDate: '2712',
        currencyCode: '840',
        transactionAmount: 1000,
        deviceManufacturerIdentifier: '040010030273',
        paymentDataType: '3DSecure',
        paymentData: {
          onlinePaymentCryptogram: 'AgAAAAAABk4D...',
          eciIndicator: '05',
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
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

