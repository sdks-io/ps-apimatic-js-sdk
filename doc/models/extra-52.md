
# Extra 52

*This model accepts additional fields of type unknown.*

## Structure

`Extra52`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `expiryMonth` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `cardIssuer` | `string` | Required | - |
| `maskedPan` | `string` | Required | - |
| `cardBrand` | `string` | Required | - |
| `cardIssuerCountry` | `string` | Required | - |
| `cardType` | `string` | Required | - |
| `cardholderName` | `string` | Required | - |
| `expiryYear` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Extra52 } from 'ps-apimatic-sdk';

const extra52: Extra52 = {
  expiryMonth: '07',
  amount: 22,
  cardIssuer: 'CIAGROUP',
  maskedPan: '55555555****4444',
  cardBrand: 'MASTER',
  cardIssuerCountry: 'BR',
  cardType: 'DEBIT',
  cardholderName: 'rahul',
  expiryYear: '30',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

