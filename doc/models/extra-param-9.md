
# Extra Param 9

*This model accepts additional fields of type unknown.*

## Structure

`ExtraParam9`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `clientFee` | `number` | Required | - |
| `toAddress` | [`ToAddress1[]`](../../doc/models/to-address-1.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ExtraParam9 } from 'ps-apimatic-sdk';

const extraParam9: ExtraParam9 = {
  clientFee: 0.1,
  toAddress: [
    {
      symbol: 'ETH',
      network: 'ETHEREUM',
      address: '0xc4db7bBB898B98D15be823454d1dff6C308BC9A4',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      symbol: 'USDC',
      network: 'POLYGON',
      address: '0xc4cs7bBB898B89D15be823445d1dff6C380BC9D3',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

