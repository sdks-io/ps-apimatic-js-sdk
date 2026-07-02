
# Delete Merchant Api

*This model accepts additional fields of type unknown.*

## Structure

`DeleteMerchantApi`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `string` | Required | - |
| `data` | [`Data5`](../../doc/models/data-5.md) | Required | - |
| `message` | `string` | Required | - |
| `reqId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { DeleteMerchantApi } from 'ps-apimatic-sdk';

const deleteMerchantApi: DeleteMerchantApi = {
  status: 'success',
  data: {
    merchantId: 4388,
    username: 'testprithvimerchant18',
    email: 'test18@paysecure.co',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  message: 'Merchant deleted successfully',
  reqId: '123',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

