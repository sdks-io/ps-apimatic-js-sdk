
# Request Global Account

*This model accepts additional fields of type unknown.*

## Structure

`RequestGlobalAccount`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `string` | Required | - |
| `data` | [`Data16`](../../doc/models/data-16.md) | Required | - |
| `message` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { RequestGlobalAccount } from 'ps-apimatic-sdk';

const requestGlobalAccount: RequestGlobalAccount = {
  status: 'success',
  data: {
    country: 'AE',
    currency: 'GBP',
    status: 'pending',
    accountNo: 'GC-AE-GBP-20260506-980-CED9D5',
    createdOn: 1778074623,
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  message: 'Global account request submitted',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

