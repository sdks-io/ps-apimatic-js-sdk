
# Pay Out Details

*This model accepts additional fields of type unknown.*

## Structure

`PayOutDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Required | - |
| `emailAddress` | `string` | Required | - |
| `secretQa` | `string` | Required | - |
| `secretAnswer` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PayOutDetails } from 'ps-apimatic-sdk';

const payOutDetails: PayOutDetails = {
  name: 'INTERAC E-TRANSFER',
  emailAddress: 'ashishm.21190@gmail.com',
  secretQa: 'q66276336575481202',
  secretAnswer: 'a66276336575481202',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

