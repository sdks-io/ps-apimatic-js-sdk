
# Client 80

*This model accepts additional fields of type unknown.*

## Structure

`Client80`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Required | - |
| `email` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `streetAddress` | `string` | Required | - |
| `country` | `string` | Required | - |
| `city` | `string` | Required | - |
| `zipCode` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client80 } from 'ps-apimatic-sdk';

const client80: Client80 = {
  customerId: '685fa7d7b93cc30dd78956c1',
  email: 'rahul+7@paysecure.net',
  phone: '+918839471520',
  fullName: 'Rahul Agarwal',
  streetAddress: 'Vaishali Jaipur',
  country: 'FR',
  city: 'jaipur',
  zipCode: '202020',
  stateCode: 'RA',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

