
# Success 32

*This model accepts additional fields of type unknown.*

## Structure

`Success32`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sessionUrl` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `customerId` | `string` | Required | - |
| `sessionId` | `string` | Required | - |
| `expiryOn` | `number` | Required | - |
| `createdOn` | `number` | Required | - |
| `expiryInMins` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success32 } from 'ps-apimatic-sdk';

const success32: Success32 = {
  sessionUrl: 'https://api.paysecure.net/api/v1/session/685bdefb9a1a8f16b3c4489c/',
  brandId: '<UUID>',
  customerId: '685bdd529a1a8f16b3c445a4',
  sessionId: '685cc8515e3af922dd0e8c31',
  expiryOn: 1750852223,
  createdOn: 1750851323,
  expiryInMins: '86400',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

