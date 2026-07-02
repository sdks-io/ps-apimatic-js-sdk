
# Gateway 2

*This model accepts additional fields of type unknown.*

## Structure

`Gateway2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `gatewayName` | `string` | Required | - |
| `status` | `string` | Required | - |
| `error` | [`Error`](../../doc/models/error.md) | Required | - |
| `balances` | `string[]` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Gateway2 } from 'ps-apimatic-sdk';

const gateway2: Gateway2 = {
  gatewayName: 'payhost',
  status: 'failed',
  error: {
    message: 'Bank does not provide balance',
    code: 'error',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  balances: [],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

