
# Extra Param 21

*This model accepts additional fields of type unknown.*

## Structure

`ExtraParam21`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `showCryptoConversion` | `string` | Required | - |
| `cryptoCurrencies` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ExtraParam21 } from 'ps-apimatic-sdk';

const extraParam21: ExtraParam21 = {
  showCryptoConversion: 'yes',
  cryptoCurrencies: '["BTC","ETH","USDT","XRP","LTC","DOGE","ETC","BNB","USDC","SOL","ADA","BCH","DASH","BTG","ZEC","DGB","EOS","XLM","TRX","QTUM","POL","SHIB","LINK","DAI","TON","AVAX","FDUSD","ARB","OP"]',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

