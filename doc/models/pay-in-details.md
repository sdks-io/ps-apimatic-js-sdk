
# Pay in Details

*This model accepts additional fields of type unknown.*

## Structure

`PayInDetails`

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
import { PayInDetails } from 'ps-apimatic-sdk';

const payInDetails: PayInDetails = {
  name: 'INTERAC',
  emailAddress: 'transfer@ieft.ca',
  secretQa: '66a8c78af1fc2f768304bce4',
  secretAnswer: 'ps8766a8af',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

