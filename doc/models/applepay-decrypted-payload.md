
# Applepay Decrypted Payload

*This model accepts additional fields of type unknown.*

## Structure

`ApplepayDecryptedPayload`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `applicationPrimaryAccountNumber` | `string` | Required | - |
| `applicationExpirationDate` | `string` | Required | - |
| `currencyCode` | `string` | Required | - |
| `transactionAmount` | `number` | Required | - |
| `deviceManufacturerIdentifier` | `string` | Required | - |
| `paymentDataType` | `string` | Required | - |
| `paymentData` | [`PaymentData`](../../doc/models/payment-data.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ApplepayDecryptedPayload } from 'ps-apimatic-sdk';

const applepayDecryptedPayload: ApplepayDecryptedPayload = {
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
};
```

