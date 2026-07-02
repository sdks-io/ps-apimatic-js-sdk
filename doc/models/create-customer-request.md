
# Create Customer Request

*This model accepts additional fields of type unknown.*

## Structure

`CreateCustomerRequest`

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
| `merchantCustomerId` | `string` | Required | - |
| `extraParam` | [`ExtraParam10`](../../doc/models/extra-param-10.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreateCustomerRequest } from 'ps-apimatic-sdk';

const createCustomerRequest: CreateCustomerRequest = {
  fullName: 'Rahul Agarwal',
  emailId: 'rahul+26@paysecure.net',
  dateOfBirth: '1994-06-03',
  phoneNo: '+91 797639082',
  city: 'Jaipur',
  stateCode: 'RJ',
  zipCode: '302018',
  address: 'House Number 53, Vaishali Nagar, Jaipur',
  country: 'IN',
  merchantCustomerId: 'rahultestcustomer@paysecure.net',
  extraParam: {
    param1: 'value1',
    param2: 'value2',
    param3: 'value3',
    param4: 'value4',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

