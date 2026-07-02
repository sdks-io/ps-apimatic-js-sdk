
# Metadata

*This model accepts additional fields of type unknown.*

## Structure

`Metadata`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `hasSubtransactions` | `boolean` | Required | - |
| `totalSubtransactions` | `number` | Required | - |
| `transactionHierarchyLevel` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Metadata } from 'ps-apimatic-sdk';

const metadata: Metadata = {
  hasSubtransactions: false,
  totalSubtransactions: 0,
  transactionHierarchyLevel: 'parent',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

