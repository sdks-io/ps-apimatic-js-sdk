
# Extra Param 25

*This model accepts additional fields of type unknown.*

## Structure

`ExtraParam25`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tokenReference` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ExtraParam25 } from 'ps-apimatic-sdk';

const extraParam25: ExtraParam25 = {
  tokenReference: 'token_ref',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

