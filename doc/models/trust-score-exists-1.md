
# Trust Score Exists 1

*This model accepts additional fields of type unknown.*

## Structure

`TrustScoreExists1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `transactionAllowed` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { TrustScoreExists1 } from 'ps-apimatic-sdk';

const trustScoreExists1: TrustScoreExists1 = {
  transactionAllowed: 'YES',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

