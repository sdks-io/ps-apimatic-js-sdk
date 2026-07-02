
# Data 18

*This model accepts additional fields of type unknown.*

## Structure

`Data18`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `updatedCount` | `number` | Required | - |
| `skippedTransactionIds` | `string[]` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Data18 } from 'ps-apimatic-sdk';

const data18: Data18 = {
  updatedCount: 1,
  skippedTransactionIds: [
    'temp'
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

