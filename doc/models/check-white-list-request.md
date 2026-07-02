
# Check White List Request

*This model accepts additional fields of type unknown.*

## Structure

`CheckWhiteListRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `string` | Required | - |
| `cardNum` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CheckWhiteListRequest } from 'ps-apimatic-sdk';

const checkWhiteListRequest: CheckWhiteListRequest = {
  email: 'dev@paysecure.net',
  cardNum: '5178006985381351',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

