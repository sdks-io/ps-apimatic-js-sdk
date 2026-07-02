
# Extra Param 5

*This model accepts additional fields of type unknown.*

## Structure

`ExtraParam5`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `applepayParam` | [`ApplepayParam1`](../../doc/models/applepay-param-1.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ExtraParam5 } from 'ps-apimatic-sdk';

const extraParam5: ExtraParam5 = {
  applepayParam: {
    applepayDecryptedPayload: {
      applicationPrimaryAccountNumber: '4111111111111111',
      applicationExpirationDate: '2712',
      currencyCode: '840',
      transactionAmount: 1000,
      deviceManufacturerIdentifier: '040010030273',
      paymentDataType: '3DSecure',
      paymentData: {
        onlinePaymentCryptogram: 'AgAAAAAABk4D...',
        eciIndicator: '05',
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
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

