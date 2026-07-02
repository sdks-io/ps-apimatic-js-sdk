
# Success 19

*This model accepts additional fields of type unknown.*

## Structure

`Success19`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Required | - |
| `merchantCustomerId` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `emailId` | `string` | Required | - |
| `dateOfBirth` | `string` | Required | - |
| `phoneNo` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `city` | `string` | Required | - |
| `zipCode` | `string` | Required | - |
| `address` | `string` | Required | - |
| `country` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `custRegDate` | `string` | Required | - |
| `successTrans` | `number` | Required | - |
| `createdOn` | `number` | Required | - |
| `lastUpdated` | `number` | Required | - |
| `lastActivity` | `number` | Required | - |
| `extraParam` | [`ExtraParam10`](../../doc/models/extra-param-10.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success19 } from 'ps-apimatic-sdk';

const success19: Success19 = {
  customerId: '691afbc6fd96d34a8113a34d',
  merchantCustomerId: 'rahultestcustomer@paysecure.net',
  fullName: 'Rahul Agarwal',
  emailId: 'rahul+26@paysecure.net',
  dateOfBirth: '1994-06-03',
  phoneNo: '+91 797639082',
  brandId: '1d666074-39be-4b90-aec9-e9de78fbdcb9',
  city: 'Jaipur',
  zipCode: '302018',
  address: 'House Number 53, Vaishali Nagar, Jaipur',
  country: 'IN',
  stateCode: 'RJ',
  custRegDate: '2023-12-27',
  successTrans: 0,
  createdOn: 1763376070,
  lastUpdated: 0,
  lastActivity: 1763376070,
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

