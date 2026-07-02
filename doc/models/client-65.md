
# Client 65

*This model accepts additional fields of type unknown.*

## Structure

`Client65`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `string` | Required | - |
| `country` | `string` | Required | - |
| `city` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `streetAddress` | `string` | Required | - |
| `zipCode` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client65 } from 'ps-apimatic-sdk';

const client65: Client65 = {
  email: 'example22@paysecure.net',
  country: 'IN',
  city: '123',
  stateCode: 'ca',
  streetAddress: 'test test',
  zipCode: '234567',
  phone: '9999999999',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

