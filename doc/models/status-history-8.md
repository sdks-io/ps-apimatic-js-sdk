
# Status History 8

*This model accepts additional fields of type unknown.*

## Structure

`StatusHistory8`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `type` | `string` | Required | - |
| `status` | `string` | Required | - |
| `timestamp` | `number` | Required | - |
| `updatedBy` | `string \| null` | Required | - |
| `paidReason` | `string \| null` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { StatusHistory8 } from 'ps-apimatic-sdk';

const statusHistory8: StatusHistory8 = {
  type: 'Status',
  status: 'created',
  timestamp: 1775047222,
  updatedBy: 'updatedBy6',
  paidReason: 'paidReason6',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

