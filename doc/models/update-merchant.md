
# Update Merchant

*This model accepts additional fields of type unknown.*

## Structure

`UpdateMerchant`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `string` | Required | - |
| `data` | [`Data7`](../../doc/models/data-7.md) | Required | - |
| `message` | `string` | Required | - |
| `reqId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { UpdateMerchant } from 'ps-apimatic-sdk';

const updateMerchant: UpdateMerchant = {
  status: 'success',
  data: {
    merchantId: 4389,
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  message: 'Merchant details updated successfully',
  reqId: '123',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

