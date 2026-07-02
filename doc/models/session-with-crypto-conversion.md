
# Session with Crypto Conversion

*This model accepts additional fields of type unknown.*

## Structure

`SessionWithCryptoConversion`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sessionUrl` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `customerId` | `string` | Required | - |
| `sessionId` | `string` | Required | - |
| `expiryOn` | `number` | Required | - |
| `createdOn` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { SessionWithCryptoConversion } from 'ps-apimatic-sdk';

const sessionWithCryptoConversion: SessionWithCryptoConversion = {
  sessionUrl: 'https://api.paysecure.net/payment-session/691b02b48c73dd76eedaa379/',
  brandId: 'brand_id_value',
  customerId: '68fed1855ebbe829416b08c6',
  sessionId: '691b02b48c73dd76eedaa379',
  expiryOn: 1763378744,
  createdOn: 1763377844,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

