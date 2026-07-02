
# Create Brand Id

*This model accepts additional fields of type unknown.*

## Structure

`CreateBrandId`

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
import { CreateBrandId } from 'ps-apimatic-sdk';

const createBrandId: CreateBrandId = {
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
  message: 'Brand created successfully',
  reqId: '123',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

