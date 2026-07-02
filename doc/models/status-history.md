
# Status History

*This model accepts additional fields of type unknown.*

## Structure

`StatusHistory`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `string` | Required | - |
| `timestamp` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { StatusHistory } from 'ps-apimatic-sdk';

const statusHistory: StatusHistory = {
  status: 'created',
  timestamp: 1780295331,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

