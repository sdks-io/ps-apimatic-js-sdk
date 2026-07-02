
# Extra Param 2

*This model accepts additional fields of type unknown.*

## Structure

`ExtraParam2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `googlepayParam` | [`GooglepayParam`](../../doc/models/googlepay-param.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ExtraParam2 } from 'ps-apimatic-sdk';

const extraParam2: ExtraParam2 = {
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
};
```

