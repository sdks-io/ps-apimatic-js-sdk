
# Get Global Accounts

*This model accepts additional fields of type unknown.*

## Structure

`GetGlobalAccounts`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `string` | Required | - |
| `data` | [`Data16[]`](../../doc/models/data-16.md) | Required | - |
| `message` | `string` | Required | - |
| `reqId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { GetGlobalAccounts } from 'ps-apimatic-sdk';

const getGlobalAccounts: GetGlobalAccounts = {
  status: 'success',
  data: [
    {
      country: 'FR',
      currency: 'GBP',
      status: 'pending',
      accountNo: 'GC-FR-GBP-20260409-980-FE2004',
      createdOn: 1775732111,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      country: 'AE',
      currency: 'AED',
      status: 'active',
      accountNo: 'GC-AE-AED-20260504-980-54FA8D',
      createdOn: 1777887002,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      country: 'AE',
      currency: 'GBP',
      status: 'pending',
      accountNo: 'GC-AE-GBP-20260506-980-CED9D5',
      createdOn: 1778074623,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  message: 'Global collection fetched successfully',
  reqId: '12331',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

