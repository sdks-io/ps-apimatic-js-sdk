
# Extra Param 20

*This model accepts additional fields of type unknown.*

## Structure

`ExtraParam20`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `param1` | `string` | Required | - |
| `showCryptoConversion` | `string` | Required | - |
| `cryptoCurrencies` | `string` | Required | - |
| `param3` | `string` | Required | - |
| `param4` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ExtraParam20 } from 'ps-apimatic-sdk';

const extraParam20: ExtraParam20 = {
  param1: 'value1',
  showCryptoConversion: 'yes',
  cryptoCurrencies: '["BTC","ETH","USDT","XRP","LTC","DOGE","ETC","BNB","USDC","SOL","ADA","BCH","DASH","BTG","ZEC","DGB","EOS","XLM","TRX","QTUM","POL","SHIB","LINK","DAI","TON","AVAX","FDUSD","ARB","OP"]',
  param3: 'value3',
  param4: 'value4',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

