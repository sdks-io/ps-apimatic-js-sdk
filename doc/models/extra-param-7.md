
# Extra Param 7

*This model accepts additional fields of type unknown.*

## Structure

`ExtraParam7`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payId` | `string` | Required | - |
| `bankName` | `string` | Required | - |
| `accountName` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ExtraParam7 } from 'ps-apimatic-sdk';

const extraParam7: ExtraParam7 = {
  payId: 'KeU6r2egQmQZeqUfkPYC7HSU1EDrn2GYyU',
  bankName: 'test bank name',
  accountName: 'arun',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

