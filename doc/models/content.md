
# Content

*This model accepts additional fields of type unknown.*

## Structure

`Content`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `transactionId` | `string` | Required | - |
| `status` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Content } from 'ps-apimatic-sdk';

const content: Content = {
  transactionId: '69e2146828bea6ca2e31bc85',
  status: 'paid',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

