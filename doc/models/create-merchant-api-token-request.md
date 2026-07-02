
# Create Merchant Api Token Request

*This model accepts additional fields of type unknown.*

## Structure

`CreateMerchantApiTokenRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiLabel` | `string` | Required | - |
| `isSandbox` | `boolean` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreateMerchantApiTokenRequest } from 'ps-apimatic-sdk';

const createMerchantApiTokenRequest: CreateMerchantApiTokenRequest = {
  apiLabel: 'testlabel18',
  isSandbox: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

