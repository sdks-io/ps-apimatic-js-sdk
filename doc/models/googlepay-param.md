
# Googlepay Param

*This model accepts additional fields of type unknown.*

## Structure

`GooglepayParam`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `googleMerchantId` | `string` | Required | - |
| `googlepayEncryptedPayload` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { GooglepayParam } from 'ps-apimatic-sdk';

const googlepayParam: GooglepayParam = {
  googleMerchantId: 'merchant:1234567890',
  googlepayEncryptedPayload: '{"signature":"MEUCIQC...","intermediateSigningKey":{...},"protocolVersion":"ECv2","signedMessage":"{...}"}',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

