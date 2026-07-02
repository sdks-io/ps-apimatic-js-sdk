
# Delete Merchant Token

*This model accepts additional fields of type unknown.*

## Structure

`DeleteMerchantToken`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `string` | Required | - |
| `data` | [`Data13`](../../doc/models/data-13.md) | Required | - |
| `message` | `string` | Required | - |
| `reqId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { DeleteMerchantToken } from 'ps-apimatic-sdk';

const deleteMerchantToken: DeleteMerchantToken = {
  status: 'success',
  data: {
    merchantId: 4389,
    username: 'testprithvimerchant18',
    email: 'email6',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  message: 'Merchant token deleted successfully',
  reqId: '123',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

