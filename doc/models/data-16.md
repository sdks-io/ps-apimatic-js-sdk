
# Data 16

*This model accepts additional fields of type unknown.*

## Structure

`Data16`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `country` | `string` | Required | - |
| `currency` | `string` | Required | - |
| `status` | `string` | Required | - |
| `accountNo` | `string` | Required | - |
| `createdOn` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Data16 } from 'ps-apimatic-sdk';

const data16: Data16 = {
  country: 'AE',
  currency: 'GBP',
  status: 'pending',
  accountNo: 'GC-AE-GBP-20260506-980-CED9D5',
  createdOn: 1778074623,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

