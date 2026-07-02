
# Create Merchant Api

*This model accepts additional fields of type unknown.*

## Structure

`CreateMerchantApi`

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
import { CreateMerchantApi } from 'ps-apimatic-sdk';

const createMerchantApi: CreateMerchantApi = {
  status: 'success',
  data: {
    merchantId: 4389,
    username: 'testprithvimerchant18',
    email: 'test18@paysecure.co',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  message: 'Merchant created successfully',
  reqId: 'abcd',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

