
# Applepay Param

*This model accepts additional fields of type unknown.*

## Structure

`ApplepayParam`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `applepayToken` | [`ApplepayToken`](../../doc/models/applepay-token.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ApplepayParam } from 'ps-apimatic-sdk';

const applepayParam: ApplepayParam = {
  applepayToken: {
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
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

