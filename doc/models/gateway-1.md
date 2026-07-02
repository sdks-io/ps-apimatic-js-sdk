
# Gateway 1

*This model accepts additional fields of type unknown.*

## Structure

`Gateway1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `gatewayName` | `string` | Required | - |
| `status` | `string` | Required | - |
| `error` | [`Gateway1Error`](../../doc/models/containers/gateway-1-error.md) | Required | This is a container for one-of cases. |
| `balances` | [`Gateway1Balances[]`](../../doc/models/containers/gateway-1-balances.md) | Required | This is Array of a container for one-of cases. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Gateway1 } from 'ps-apimatic-sdk';

const gateway1: Gateway1 = {
  gatewayName: 'a55Mandate',
  status: 'failed',
  error: {
    code: 'error',
    message: 'Bank does not provide balance',
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

