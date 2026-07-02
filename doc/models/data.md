
# Data

*This model accepts additional fields of type unknown.*

## Structure

`Data`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `content` | [`Content[]`](../../doc/models/content.md) | Required | - |
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
import { Data } from 'ps-apimatic-sdk';

const data: Data = {
  content: [
    {
      transactionId: '69e2146828bea6ca2e31bc85',
      status: 'paid',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      transactionId: '69e20fd928bea6ca2e31b17c',
      status: 'paid',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  currentPage: 1,
  pageSize: 2,
  totalElements: 95,
  totalPages: 48,
  first: true,
  last: false,
  hasNext: true,
  hasPrevious: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

