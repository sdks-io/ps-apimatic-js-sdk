
# Routing Param

*This model accepts additional fields of type unknown.*

## Structure

`RoutingParam`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bankCode` | `string` | Required | - |
| `bankBranchCode` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { RoutingParam } from 'ps-apimatic-sdk';

const routingParam: RoutingParam = {
  bankCode: '897678',
  bankBranchCode: '888',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

