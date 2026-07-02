
# Reject Payout with Remarks Request

*This model accepts additional fields of type unknown.*

## Structure

`RejectPayoutWithRemarksRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `remarks` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { RejectPayoutWithRemarksRequest } from 'ps-apimatic-sdk';

const rejectPayoutWithRemarksRequest: RejectPayoutWithRemarksRequest = {
  remarks: 'Failed KYC verification',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

