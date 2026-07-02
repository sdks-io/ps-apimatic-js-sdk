
# Purchase 62

*This model accepts additional fields of type unknown.*

## Structure

`Purchase62`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currency` | `string` | Required | - |
| `products` | [`Product2[]`](../../doc/models/product-2.md) | Required | - |
| `total` | `number` | Required | - |
| `language` | `string` | Required | - |
| `notes` | `string` | Required | - |
| `debt` | `number` | Required | - |
| `totalFormatted` | `number` | Required | - |
| `expireInMin` | `string` | Required | - |
| `requestClientDetails` | `string[]` | Required | - |
| `timezone` | `string` | Required | - |
| `emailMessage` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Purchase62 } from 'ps-apimatic-sdk';

const purchase62: Purchase62 = {
  currency: 'INR',
  products: [
    {
      name: 'test',
      quantity: 1,
      price: 10,
      discount: 0,
      taxPercent: '0.00',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  total: 10,
  language: 'en',
  notes: '',
  debt: 0,
  totalFormatted: 1,
  expireInMin: '35',
  requestClientDetails: [],
  timezone: 'MIT',
  emailMessage: '',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

