
# Pay Out Details 1

*This model accepts additional fields of type unknown.*

## Structure

`PayOutDetails1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `emailAddress` | `string` | Required | - |
| `secretQa` | `string` | Required | - |
| `secretAnswer` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PayOutDetails1 } from 'ps-apimatic-sdk';

const payOutDetails1: PayOutDetails1 = {
  emailAddress: 'ashishm.21190@gmail.com',
  secretQa: 'q670200747066759362',
  secretAnswer: 'a670200747066759362',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

