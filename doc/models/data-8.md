
# Data 8

*This model accepts additional fields of type unknown.*

## Structure

`Data8`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `number` | Required | - |
| `apiKey` | `string` | Required | - |
| `isSandbox` | `boolean` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Data8 } from 'ps-apimatic-sdk';

const data8: Data8 = {
  merchantId: 4389,
  apiKey: 'baf09d9df4bfae6af3db9901bb22ab235b8eb8104f6c45f97570104c31b1cd4c',
  isSandbox: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

