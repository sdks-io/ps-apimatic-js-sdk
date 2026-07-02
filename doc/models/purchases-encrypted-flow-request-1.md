
# Purchases Encrypted Flow Request 1

*This model accepts additional fields of type unknown.*

## Structure

`PurchasesEncryptedFlowRequest1`

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
| `extraParam` | [`ExtraParam4`](../../doc/models/extra-param-4.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PurchasesEncryptedFlowRequest1 } from 'ps-apimatic-sdk';

const purchasesEncryptedFlowRequest1: PurchasesEncryptedFlowRequest1 = {
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
      applepayToken: {
        version: 'EC_v1',
        data: '...',
        signature: '...',
        header: {
          ephemeralPublicKey: '...',
          publicKeyHash: '...',
          transactionId: '...',
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

