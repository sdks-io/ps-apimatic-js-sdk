
# Capture Request

*This model accepts additional fields of type unknown.*

## Structure

`CaptureRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantReference` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CaptureRequest } from 'ps-apimatic-sdk';

const captureRequest: CaptureRequest = {
  merchantReference: '64534345',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

