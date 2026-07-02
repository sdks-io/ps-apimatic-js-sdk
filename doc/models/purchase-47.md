
# Purchase 47

*This model accepts additional fields of type unknown.*

## Structure

`Purchase47`

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
| `taxAmount` | `number` | Required | - |
| `taxPercent` | `number` | Required | - |
| `requestClientDetails` | `string[]` | Required | - |
| `timezone` | `string` | Required | - |
| `emailMessage` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Purchase47 } from 'ps-apimatic-sdk';

const purchase47: Purchase47 = {
  currency: 'AUD',
  products: [
    {
      name: 'test',
      quantity: 1,
      price: 100,
      discount: 0,
      taxPercent: '0.00',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  total: 100,
  language: 'en',
  notes: '',
  debt: 0,
  totalFormatted: 1,
  taxAmount: 0,
  taxPercent: 0,
  requestClientDetails: [],
  timezone: 'MIT',
  emailMessage: '',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

