
# Bulk Update Invoice No

*This model accepts additional fields of type unknown.*

## Structure

`BulkUpdateInvoiceNo`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `string` | Required | - |
| `data` | [`Data18`](../../doc/models/data-18.md) | Required | - |
| `message` | `string` | Required | - |
| `reqId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { BulkUpdateInvoiceNo } from 'ps-apimatic-sdk';

const bulkUpdateInvoiceNo: BulkUpdateInvoiceNo = {
  status: 'success',
  data: {
    updatedCount: 1,
    skippedTransactionIds: [
      'temp'
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  message: 'Bulk invoice update completed',
  reqId: 'abcd',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

