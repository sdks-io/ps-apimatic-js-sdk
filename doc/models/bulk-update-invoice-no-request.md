
# Bulk Update Invoice No Request

*This model accepts additional fields of type unknown.*

## Structure

`BulkUpdateInvoiceNoRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `transactionId` | `string` | Required | - |
| `invoiceNo` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { BulkUpdateInvoiceNoRequest } from 'ps-apimatic-sdk';

const bulkUpdateInvoiceNoRequest: BulkUpdateInvoiceNoRequest = {
  transactionId: '69cceeba4235594c8159559f',
  invoiceNo: 'inv123',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

