
# Data 5

*This model accepts additional fields of type unknown.*

## Structure

`Data5`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `number` | Required | - |
| `username` | `string` | Required | - |
| `email` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Data5 } from 'ps-apimatic-sdk';

const data5: Data5 = {
  merchantId: 4388,
  username: 'testprithvimerchant18',
  email: 'test18@paysecure.co',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

