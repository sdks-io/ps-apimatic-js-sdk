
# Extra Param 6

*This model accepts additional fields of type unknown.*

## Structure

`ExtraParam6`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `isCryptoPurchase` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ExtraParam6 } from 'ps-apimatic-sdk';

const extraParam6: ExtraParam6 = {
  isCryptoPurchase: 'yes',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

