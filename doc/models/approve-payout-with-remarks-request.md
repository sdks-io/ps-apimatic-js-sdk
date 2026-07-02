
# Approve Payout with Remarks Request

*This model accepts additional fields of type unknown.*

## Structure

`ApprovePayoutWithRemarksRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `remarks` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ApprovePayoutWithRemarksRequest } from 'ps-apimatic-sdk';

const approvePayoutWithRemarksRequest: ApprovePayoutWithRemarksRequest = {
  remarks: 'Verified against invoice #4821',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

