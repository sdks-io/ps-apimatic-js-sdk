
# Get Settlement Data

*This model accepts additional fields of type unknown.*

## Structure

`GetSettlementData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `string` | Required | - |
| `data` | [`Data12`](../../doc/models/data-12.md) | Required | - |
| `reqId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { GetSettlementData } from 'ps-apimatic-sdk';

const getSettlementData: GetSettlementData = {
  status: 'success',
  data: {
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
  },
  reqId: '123456',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

