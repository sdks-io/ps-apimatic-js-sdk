
# Extra

*This model accepts additional fields of type unknown.*

## Structure

`Extra`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `expiryMonth` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `cardIssuer` | `string` | Required | - |
| `maskedPan` | `string` | Required | - |
| `cardBrand` | `string` | Required | - |
| `cardIssuerCountry` | `string` | Required | - |
| `cardholderName` | `string` | Required | - |
| `expiryYear` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Extra } from 'ps-apimatic-sdk';

const extra: Extra = {
  expiryMonth: '10',
  amount: 100,
  cardIssuer: '1-800-432-3117',
  maskedPan: '411111XXXXXX1111',
  cardBrand: 'VISA',
  cardIssuerCountry: 'US',
  cardholderName: 'dk',
  expiryYear: '23',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

