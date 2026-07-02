
# Data 12

*This model accepts additional fields of type unknown.*

## Structure

`Data12`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `settlements` | [`Settlement[]`](../../doc/models/settlement.md) | Required | - |
| `pagination` | [`Pagination`](../../doc/models/pagination.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Data12 } from 'ps-apimatic-sdk';

const data12: Data12 = {
  settlements: [
    {
      settlementId: '1234',
      amount: 100,
      currency: 'USD',
      status: 'settled',
      settledOn: -41795,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      settlementId: '5678',
      amount: 100,
      currency: 'USD',
      status: 'settled',
      settledOn: -41795,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  pagination: {
    currentPage: 1,
    pageSize: 2,
    totalElements: 2,
    totalPages: 1,
    first: true,
    last: true,
    hasNext: false,
    hasPrevious: false,
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

