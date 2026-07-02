
# Data 14

*This model accepts additional fields of type unknown.*

## Structure

`Data14`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `number` | Required | - |
| `name` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `merchantId` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Data14 } from 'ps-apimatic-sdk';

const data14: Data14 = {
  id: 1000077,
  name: 'Sample brand name2',
  brandId: '1d01b37c-bd35-4727-85f9-f0b1448dad67',
  merchantId: 4230,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

