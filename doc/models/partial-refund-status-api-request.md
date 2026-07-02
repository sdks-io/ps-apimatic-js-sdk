
# Partial Refund Status Api Request

*This model accepts additional fields of type unknown.*

## Structure

`PartialRefundStatusApiRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `refundId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PartialRefundStatusApiRequest } from 'ps-apimatic-sdk';

const partialRefundStatusApiRequest: PartialRefundStatusApiRequest = {
  refundId: 'refundid',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

