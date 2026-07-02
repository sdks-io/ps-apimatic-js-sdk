
# Applepay Token

*This model accepts additional fields of type unknown.*

## Structure

`ApplepayToken`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `version` | `string` | Required | - |
| `data` | `string` | Required | - |
| `signature` | `string` | Required | - |
| `header` | [`Header`](../../doc/models/header.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ApplepayToken } from 'ps-apimatic-sdk';

const applepayToken: ApplepayToken = {
  version: 'EC_v1',
  data: '...',
  signature: '...',
  header: {
    ephemeralPublicKey: '...',
    publicKeyHash: '...',
    transactionId: '...',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

