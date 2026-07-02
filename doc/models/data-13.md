
# Data 13

*This model accepts additional fields of type unknown.*

## Structure

`Data13`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `number` | Required | - |
| `username` | `string` | Required | - |
| `email` | `string \| null` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Data13 } from 'ps-apimatic-sdk';

const data13: Data13 = {
  merchantId: 4389,
  username: 'testprithvimerchant18',
  email: 'email6',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

