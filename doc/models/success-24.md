
# Success 24

*This model accepts additional fields of type unknown.*

## Structure

`Success24`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentMethod` | `string` | Required | - |
| `status` | `string` | Required | - |
| `data` | [`Datum[]`](../../doc/models/datum.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success24 } from 'ps-apimatic-sdk';

const success24: Success24 = {
  paymentMethod: 'BANKTRANSFER',
  status: 'success',
  data: [
    {
      currency: 'AUD',
      balance: '0.00',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      currency: 'USD',
      balance: '46813.79',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      currency: 'JPY',
      balance: '1012.00',
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

