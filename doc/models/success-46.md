
# Success 46

*This model accepts additional fields of type unknown.*

## Structure

`Success46`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cardLastFour` | `string` | Required | - |
| `tokenReference` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success46 } from 'ps-apimatic-sdk';

const success46: Success46 = {
  cardLastFour: '1003',
  tokenReference: 'token_2bcf691f0f0347d6bcb38118d1bb31d5',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

