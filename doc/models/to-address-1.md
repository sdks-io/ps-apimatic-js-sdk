
# To Address 1

*This model accepts additional fields of type unknown.*

## Structure

`ToAddress1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `symbol` | `string` | Required | - |
| `network` | `string` | Required | - |
| `address` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ToAddress1 } from 'ps-apimatic-sdk';

const toAddress1: ToAddress1 = {
  symbol: 'ETH',
  network: 'ETHEREUM',
  address: '0xc4db7bBB898B98D15be823454d1dff6C308BC9A4',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

