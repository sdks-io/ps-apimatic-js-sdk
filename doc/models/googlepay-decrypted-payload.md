
# Googlepay Decrypted Payload

*This model accepts additional fields of type unknown.*

## Structure

`GooglepayDecryptedPayload`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `messageExpiration` | `string` | Required | - |
| `messageId` | `string` | Required | - |
| `paymentMethod` | `string` | Required | - |
| `paymentMethodDetails` | [`PaymentMethodDetails`](../../doc/models/payment-method-details.md) | Required | - |
| `gatewayMerchantId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { GooglepayDecryptedPayload } from 'ps-apimatic-sdk';

const googlepayDecryptedPayload: GooglepayDecryptedPayload = {
  messageExpiration: '1735689600000',
  messageId: 'AH2EjtfkYz...',
  paymentMethod: 'CARD',
  paymentMethodDetails: {
    pan: '4111111111111111',
    expirationMonth: 12,
    expirationYear: 2027,
    authMethod: 'CRYPTOGRAM_3DS',
    cryptogram: 'AgAAAAAABk4D...',
    eciIndicator: '05',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  gatewayMerchantId: 'your_gateway_merchant_id',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

