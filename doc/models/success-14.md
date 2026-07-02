
# Success 14

*This model accepts additional fields of type unknown.*

## Structure

`Success14`

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
import { Success14 } from 'ps-apimatic-sdk';

const success14: Success14 = {
  sessionUrl: 'https://api.choicepay.ca/payment-session/6963533a0a18ea65153a81e7/',
  brandId: 'brand_id_value',
  customerId: '69034a5a61b460084d20c23b',
  sessionId: '6963533a0a18ea65153a81e7',
  expiryOn: 1768117950,
  createdOn: 1768117050,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

