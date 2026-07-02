
# Extra Param 1

*This model accepts additional fields of type unknown.*

## Structure

`ExtraParam1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `reference` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ExtraParam1 } from 'ps-apimatic-sdk';

const extraParam1: ExtraParam1 = {
  reference: 'wkdjabf43',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

