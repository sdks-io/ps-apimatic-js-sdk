
# S2 S Payment Request

*This model accepts additional fields of type unknown.*

## Structure

`S2SPaymentRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tokenReference` | `string` | Required | - |
| `cvc` | `string` | Required | - |
| `rememberCard` | `string` | Required | - |
| `remoteIp` | `string` | Required | - |
| `userAgent` | `string` | Required | - |
| `acceptHeader` | `string` | Required | - |
| `language` | `string` | Required | - |
| `javaEnabled` | `boolean` | Required | - |
| `javascriptEnabled` | `boolean` | Required | - |
| `colorDepth` | `number` | Required | - |
| `utcOffset` | `number` | Required | - |
| `screenWidth` | `number` | Required | - |
| `screenHeight` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { S2SPaymentRequest } from 'ps-apimatic-sdk';

const s2SPaymentRequest: S2SPaymentRequest = {
  tokenReference: 'token_7178aa7208614544a285656da38ae5ac',
  cvc: '791',
  rememberCard: 'off',
  remoteIp: '157.38.242.7',
  userAgent: 'Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/51.0.2704.103 Safari/537.36',
  acceptHeader: 'text/html',
  language: 'en-US',
  javaEnabled: false,
  javascriptEnabled: true,
  colorDepth: 24,
  utcOffset: 0,
  screenWidth: 1920,
  screenHeight: 1080,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

