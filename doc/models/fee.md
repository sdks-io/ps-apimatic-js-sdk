
# Fee

*This model accepts additional fields of type unknown.*

## Structure

`Fee`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `type` | `string` | Required | - |
| `amount` | [`FeeAmount`](../../doc/models/containers/fee-amount.md) | Required | This is a container for one-of cases. |
| `currency` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Fee } from 'ps-apimatic-sdk';

const fee: Fee = {
  type: 'mdr',
  amount: 0,
  currency: 'USD',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

