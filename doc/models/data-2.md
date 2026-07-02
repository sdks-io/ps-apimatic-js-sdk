
# Data 2

*This model accepts additional fields of type unknown.*

## Structure

`Data2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `transactionId` | `string` | Required | - |
| `merchantReference` | `string` | Required | - |
| `customerId` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `currency` | `string` | Required | - |
| `status` | `string` | Required | - |
| `sessionId` | `string` | Required | - |
| `email` | `string` | Required | - |
| `merchantName` | `string` | Required | - |
| `paymentMethod` | `string` | Required | - |
| `paymentFlow` | `string` | Required | - |
| `issuingBank` | `string` | Required | - |
| `createdAt` | `string` | Required | - |
| `errorReason` | `string` | Required | - |
| `lastUpdatedAt` | `string` | Required | - |
| `transactionType` | `string` | Required | - |
| `fees` | [`Fee[]`](../../doc/models/fee.md) | Required | - |
| `metadata` | [`Metadata`](../../doc/models/metadata.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Data2 } from 'ps-apimatic-sdk';

const data2: Data2 = {
  transactionId: 'transaction_id8',
  merchantReference: 'merchant_reference2',
  customerId: 'customer_id8',
  amount: 194.12,
  currency: 'currency0',
  status: 'status2',
  sessionId: 'session_id2',
  email: 'email6',
  merchantName: 'merchant_name2',
  paymentMethod: 'payment_method0',
  paymentFlow: 'payment_flow4',
  issuingBank: 'issuing_bank0',
  createdAt: 'created_at8',
  errorReason: 'error_reason2',
  lastUpdatedAt: 'last_updated_at8',
  transactionType: 'transaction_type2',
  fees: [
    {
      type: 'mdr',
      amount: 0,
      currency: 'USD',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  metadata: {
    hasSubtransactions: false,
    totalSubtransactions: 0,
    transactionHierarchyLevel: 'parent',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

