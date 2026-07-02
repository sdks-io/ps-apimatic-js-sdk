
# Pay Out Details 3

*This model accepts additional fields of type unknown.*

## Structure

`PayOutDetails3`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `instruction` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PayOutDetails3 } from 'ps-apimatic-sdk';

const payOutDetails3: PayOutDetails3 = {
  instruction: 'Please use transaction reference 20514294 with the BTC 77361 at any Fawry store to get cashout within 72 hrs',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

