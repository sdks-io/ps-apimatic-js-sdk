
# Pagination

*This model accepts additional fields of type unknown.*

## Structure

`Pagination`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currentPage` | `number` | Required | - |
| `pageSize` | `number` | Required | - |
| `totalElements` | `number` | Required | - |
| `totalPages` | `number` | Required | - |
| `first` | `boolean` | Required | - |
| `last` | `boolean` | Required | - |
| `hasNext` | `boolean` | Required | - |
| `hasPrevious` | `boolean` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Pagination } from 'ps-apimatic-sdk';

const pagination: Pagination = {
  currentPage: 1,
  pageSize: 30,
  totalElements: 44,
  totalPages: 2,
  first: true,
  last: false,
  hasNext: true,
  hasPrevious: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

