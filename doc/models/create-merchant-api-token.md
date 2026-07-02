
# Create Merchant Api Token

*This model accepts additional fields of type unknown.*

## Structure

`CreateMerchantApiToken`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `string` | Required | - |
| `data` | [`Data8`](../../doc/models/data-8.md) | Required | - |
| `message` | `string` | Required | - |
| `reqId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreateMerchantApiToken } from 'ps-apimatic-sdk';

const createMerchantApiToken: CreateMerchantApiToken = {
  status: 'success',
  data: {
    merchantId: 4389,
    apiKey: 'baf09d9df4bfae6af3db9901bb22ab235b8eb8104f6c45f97570104c31b1cd4c',
    isSandbox: false,
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  message: 'Merchant token generated successfully',
  reqId: 'abcd',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

