
# Get Missing Invoice Transactions

*This model accepts additional fields of type unknown.*

## Structure

`GetMissingInvoiceTransactions`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `string` | Required | - |
| `data` | [`Data11`](../../doc/models/data-11.md) | Required | - |
| `message` | `string` | Required | - |
| `reqId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { GetMissingInvoiceTransactions } from 'ps-apimatic-sdk';

const getMissingInvoiceTransactions: GetMissingInvoiceTransactions = {
  status: 'success',
  data: {
    transactions: [
      {
        transactionId: '69d79150aa6d618c9b4e5da1',
        amount: 1,
        currency: 'GBP',
        createdDate: 1775735120,
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      {
        transactionId: '69d627aafbb9070a716e284b',
        amount: 1,
        currency: 'GBP',
        createdDate: 1775642538,
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      {
        transactionId: '69d6277afbb9070a716e252b',
        amount: 1,
        currency: 'GBP',
        createdDate: 1775642490,
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      {
        transactionId: '69cced964235594c815952fc',
        amount: 1,
        currency: 'GBP',
        createdDate: 1775037848,
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    pagination: {
      currentPage: 1,
      pageSize: 4,
      totalElements: 6,
      totalPages: 2,
      first: true,
      last: false,
      hasNext: true,
      hasPrevious: false,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  message: 'Missing invoice transactions fetched successfully',
  reqId: '123456',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

