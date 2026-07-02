
# Payout Session Request

*This model accepts additional fields of type unknown.*

## Structure

`PayoutSessionRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Required | - |
| `currency` | `string` | Required | - |
| `products` | [`Product[]`](../../doc/models/product.md) | Required | - |
| `totalAmount` | `string` | Required | - |
| `taxAmount` | `string` | Required | - |
| `taxPercent` | `string` | Required | - |
| `type` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `extraParam` | [`ExtraParam21`](../../doc/models/extra-param-21.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PayoutSessionRequest } from 'ps-apimatic-sdk';

const payoutSessionRequest: PayoutSessionRequest = {
  customerId: '67c9983fba18400ab6cceb8f',
  currency: 'USD',
  products: [
    {
      name: 'Product1',
      price: '2',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  totalAmount: '2',
  taxAmount: '',
  taxPercent: '',
  type: 'payout',
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  extraParam: {
    showCryptoConversion: 'yes',
    cryptoCurrencies: '["BTC","ETH","USDT","XRP","LTC","DOGE","ETC","BNB","USDC","SOL","ADA","BCH","DASH","BTG","ZEC","DGB","EOS","XLM","TRX","QTUM","POL","SHIB","LINK","DAI","TON","AVAX","FDUSD","ARB","OP"]',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

