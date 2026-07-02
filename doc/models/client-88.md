
# Client 88

*This model accepts additional fields of type unknown.*

## Structure

`Client88`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Required | - |
| `email` | `string` | Required | - |
| `dateOfBirth` | `string` | Required | - |
| `streetAddress` | `string` | Required | - |
| `country` | `string` | Required | - |
| `city` | `string` | Required | - |
| `zipCode` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `gender` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client88 } from 'ps-apimatic-sdk';

const client88: Client88 = {
  customerId: 'NA',
  email: 'alpha7.bravo@bravapay.com',
  dateOfBirth: '2004-04-31',
  streetAddress: '10 New Burlington StreetApt. 214',
  country: 'GB',
  city: 'London',
  zipCode: 'SW1A0AA',
  fullName: 'shiba sharma',
  phone: '+447755564318',
  gender: 'male',
  stateCode: 'LND',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

