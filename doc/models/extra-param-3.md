
# Extra Param 3

*This model accepts additional fields of type unknown.*

## Structure

`ExtraParam3`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `googlepayParam` | [`GooglepayParam1`](../../doc/models/googlepay-param-1.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ExtraParam3 } from 'ps-apimatic-sdk';

const extraParam3: ExtraParam3 = {
  googlepayParam: {
    googleMerchantId: 'merchant:1234567890',
    googlepayDecryptedPayload: {
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
    },
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

