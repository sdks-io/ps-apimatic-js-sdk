
# Whitelist Upload Success

*This model accepts additional fields of type unknown.*

## Structure

`WhitelistUploadSuccess`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `totalRecords` | `number` | Required | - |
| `totalApproved` | `number` | Required | - |
| `status` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { WhitelistUploadSuccess } from 'ps-apimatic-sdk';

const whitelistUploadSuccess: WhitelistUploadSuccess = {
  totalRecords: 3,
  totalApproved: 3,
  status: 'success',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

