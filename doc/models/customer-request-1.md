
# Customer Request 1

*This model accepts additional fields of type unknown.*

## Structure

`CustomerRequest1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `fullName` | `string` | Required | - |
| `emailId` | `string` | Required | - |
| `dateOfBirth` | `string` | Required | - |
| `phoneNo` | `string` | Required | - |
| `city` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `zipCode` | `string` | Required | - |
| `address` | `string` | Required | - |
| `country` | `string` | Required | - |
| `custRegDate` | `string` | Required | - |
| `successTxn` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CustomerRequest1 } from 'ps-apimatic-sdk';

const customerRequest1: CustomerRequest1 = {
  fullName: 'Gouri Shankar3',
  emailId: 'gouri@paysecure.com',
  dateOfBirth: '1990-11-27',
  phoneNo: '+91 9413666514',
  city: 'Dausa',
  stateCode: 'Raj',
  zipCode: '202021',
  address: 'Somnath Nagar',
  country: 'IN',
  custRegDate: '2023-12-28',
  successTxn: '33',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

