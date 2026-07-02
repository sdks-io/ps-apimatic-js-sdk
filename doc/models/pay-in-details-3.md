
# Pay in Details 3

*This model accepts additional fields of type unknown.*

## Structure

`PayInDetails3`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Required | - |
| `emailAddress` | `string` | Required | - |
| `referenceNumber` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PayInDetails3 } from 'ps-apimatic-sdk';

const payInDetails3: PayInDetails3 = {
  name: 'INTERAC E-TRANSFER',
  emailAddress: 'fund@ieft.ca',
  referenceNumber: '8g1lya',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

