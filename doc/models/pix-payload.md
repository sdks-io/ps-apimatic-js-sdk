
# Pix Payload

*This model accepts additional fields of type unknown.*

## Structure

`PixPayload`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payload` | `string` | Required | - |
| `qrCode` | `string` | Required | - |
| `expirationDate` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PixPayload } from 'ps-apimatic-sdk';

const pixPayload: PixPayload = {
  payload: '00020101021226800014br.gov.bcb.pix2558pix.asaas.com/qr/cobv/e3eb36eb-7e9b-404d-9bd3-b486a42da3445204000053039865802BR5925A55 CONSULTORIA EM CREDIT6009Sao Paulo61080455202062070503***630451CA',
  qrCode: 'iVBORw0KGgoAAAANSUhEUgAAAZ8AAAGfCAIAAAAPgEjDAAAP4UlEQVR42u3bUY7cSA4EUN … ..',
  expirationDate: '2025-03-27 23:59:59',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

