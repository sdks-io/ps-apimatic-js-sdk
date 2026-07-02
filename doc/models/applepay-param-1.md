
# Applepay Param 1

*This model accepts additional fields of type unknown.*

## Structure

`ApplepayParam1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `applepayDecryptedPayload` | [`ApplepayDecryptedPayload`](../../doc/models/applepay-decrypted-payload.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ApplepayParam1 } from 'ps-apimatic-sdk';

const applepayParam1: ApplepayParam1 = {
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
};
```

