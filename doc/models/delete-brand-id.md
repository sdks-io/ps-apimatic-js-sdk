
# Delete Brand Id

*This model accepts additional fields of type unknown.*

## Structure

`DeleteBrandId`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `string` | Required | - |
| `data` | [`Data14`](../../doc/models/data-14.md) | Required | - |
| `message` | `string` | Required | - |
| `reqId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { DeleteBrandId } from 'ps-apimatic-sdk';

const deleteBrandId: DeleteBrandId = {
  status: 'success',
  data: {
    id: 1000077,
    name: 'Sample brand name2',
    brandId: '1d01b37c-bd35-4727-85f9-f0b1448dad67',
    merchantId: 4230,
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  message: 'Brand deleted successfully',
  reqId: '123',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

