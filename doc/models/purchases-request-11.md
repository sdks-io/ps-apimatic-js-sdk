
# Purchases Request 11

*This model accepts additional fields of type unknown.*

## Structure

`PurchasesRequest11`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client8`](../../doc/models/client-8.md) | Required | - |
| `purchase` | [`Purchase48`](../../doc/models/purchase-48.md) | Required | - |
| `paymentMethod` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `extraParam` | [`ExtraParam8`](../../doc/models/extra-param-8.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PurchasesRequest11 } from 'ps-apimatic-sdk';

const purchasesRequest11: PurchasesRequest11 = {
  client: {
    email: 'gaurav@gmail.com',
    streetAddress: 'test test',
    city: '123',
    fullName: 'Gaurav Test',
    zipCode: '234567',
    country: 'US',
    stateCode: 'NYC',
    phone: '9999999999',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'product name',
        price: 5.86,
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  paymentMethod: 'CRYPTO-BRIDGE',
  brandId: 'cec67fe3-a01d-4d0d-b100-9fafb200fe15',
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  extraParam: {
    clientFee: 0.1,
    toAddress: [
      {
        symbol: 'ETH',
        networkName: 'ETHEREUM',
        address: '0xc4db7bBB898B98D15be823454d1dff6C308BC9A4',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      {
        symbol: 'USDC',
        networkName: 'POLYGON',
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
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

