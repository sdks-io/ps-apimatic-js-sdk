
# Extra Param 4

*This model accepts additional fields of type unknown.*

## Structure

`ExtraParam4`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `applepayParam` | [`ApplepayParam`](../../doc/models/applepay-param.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ExtraParam4 } from 'ps-apimatic-sdk';

const extraParam4: ExtraParam4 = {
  applepayParam: {
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
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

