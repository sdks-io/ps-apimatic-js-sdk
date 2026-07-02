
# Success 39

*This model accepts additional fields of type unknown.*

## Structure

`Success39`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mandateId` | `string` | Required | - |
| `message` | `string` | Required | - |
| `revokeDate` | `number` | Required | - |
| `status` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success39 } from 'ps-apimatic-sdk';

const success39: Success39 = {
  mandateId: '6943aabe3f5c35b0f7849768',
  message: 'Mandate revoked successfully',
  revokeDate: 1769857766,
  status: 'REVOKED',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

