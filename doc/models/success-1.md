
# Success 1

*This model accepts additional fields of type unknown.*

## Structure

`Success1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `string` | Required | - |
| `callbackUrl` | `string` | Required | - |
| `method` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success1 } from 'ps-apimatic-sdk';

const success1: Success1 = {
  status: 'pending',
  callbackUrl: 'http://18.214.100.20/api/v1/payment/64b034ecc6dccf7d329d9eb3/',
  method: 'GET',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

