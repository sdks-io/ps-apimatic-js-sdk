
# Extra Param 10

*This model accepts additional fields of type unknown.*

## Structure

`ExtraParam10`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `param1` | `string` | Required | - |
| `param2` | `string` | Required | - |
| `param3` | `string` | Required | - |
| `param4` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ExtraParam10 } from 'ps-apimatic-sdk';

const extraParam10: ExtraParam10 = {
  param1: 'value1',
  param2: 'value2',
  param3: 'value3',
  param4: 'value4',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

