
# Extra 5

*This model accepts additional fields of type unknown.*

## Structure

`Extra5`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `expiryMonth` | `string \| undefined` | Optional | - |
| `amount` | `number` | Required | - |
| `cardIssuer` | `string \| undefined` | Optional | - |
| `maskedPan` | `string \| undefined` | Optional | - |
| `cardBrand` | `string \| undefined` | Optional | - |
| `cardIssuerCountry` | `string \| undefined` | Optional | - |
| `cardholderName` | `string \| undefined` | Optional | - |
| `expiryYear` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Extra5 } from 'ps-apimatic-sdk';

const extra5: Extra5 = {
  amount: 9,
  expiryMonth: '10',
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

