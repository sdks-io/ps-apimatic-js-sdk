
# Extra Param

*This model accepts additional fields of type unknown.*

## Structure

`ExtraParam`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cardNumber` | `string` | Required | - |
| `cardHolderName` | `string` | Required | - |
| `expiryYear` | `string` | Required | - |
| `expiryMonth` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ExtraParam } from 'ps-apimatic-sdk';

const extraParam: ExtraParam = {
  cardNumber: '5431240006334004',
  cardHolderName: 'Rahul Agarwal',
  expiryYear: '2030',
  expiryMonth: '11',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

