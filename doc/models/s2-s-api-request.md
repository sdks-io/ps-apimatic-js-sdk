
# S2 S Api Request

*This model accepts additional fields of type unknown.*

## Structure

`S2SApiRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cardholderName` | `string` | Required | - |
| `cardNumber` | `string` | Required | - |
| `expires` | `string` | Required | - |
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
import { S2SApiRequest } from 'ps-apimatic-sdk';

const s2SApiRequest: S2SApiRequest = {
  cardholderName: 'dk',
  cardNumber: '4111111111111111',
  expires: '10/23',
  cvc: '345',
  rememberCard: 'on',
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

