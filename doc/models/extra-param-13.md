
# Extra Param 13

*This model accepts additional fields of type unknown.*

## Structure

`ExtraParam13`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `productType` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ExtraParam13 } from 'ps-apimatic-sdk';

const extraParam13: ExtraParam13 = {
  productType: 'WELFARE',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

