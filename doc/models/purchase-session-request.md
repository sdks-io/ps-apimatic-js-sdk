
# Purchase Session Request

*This model accepts additional fields of type unknown.*

## Structure

`PurchaseSessionRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Required | - |
| `merchantRef` | `string` | Required | - |
| `currency` | `string` | Required | - |
| `products` | [`Product[]`](../../doc/models/product.md) | Required | - |
| `totalAmount` | `string` | Required | - |
| `paymentMethod` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `extraParam` | [`ExtraParam20`](../../doc/models/extra-param-20.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PurchaseSessionRequest } from 'ps-apimatic-sdk';

const purchaseSessionRequest: PurchaseSessionRequest = {
  customerId: '68fed1855ebbe829416b08c6',
  merchantRef: 'rahultestcustomer1@paysecure.net',
  currency: 'EUR',
  products: [
    {
      name: 'Product1',
      price: '10',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      name: 'Product2',
      price: '12',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  totalAmount: '22',
  paymentMethod: 'VISA',
  successRedirect: 'https://merchant-success-page.com/',
  failureRedirect: 'https://merchant-failure-page.com/',
  pendingRedirect: 'https://merchant-pending-page.com/',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  extraParam: {
    param1: 'value1',
    showCryptoConversion: 'yes',
    cryptoCurrencies: '["BTC","ETH","USDT","XRP","LTC","DOGE","ETC","BNB","USDC","SOL","ADA","BCH","DASH","BTG","ZEC","DGB","EOS","XLM","TRX","QTUM","POL","SHIB","LINK","DAI","TON","AVAX","FDUSD","ARB","OP"]',
    param3: 'value3',
    param4: 'value4',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

