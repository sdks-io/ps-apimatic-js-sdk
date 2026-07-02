
# Client 8

*This model accepts additional fields of type unknown.*

## Structure

`Client8`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `string` | Required | - |
| `streetAddress` | `string` | Required | - |
| `city` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `zipCode` | `string` | Required | - |
| `country` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client8 } from 'ps-apimatic-sdk';

const client8: Client8 = {
  email: 'seo2009@test.com',
  streetAddress: '10 New Burlington Street Apt. 214',
  city: 'London',
  fullName: 'Test test',
  zipCode: 'W1S 3BE',
  country: 'CA',
  stateCode: 'QLD',
  phone: '+447755564318',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

