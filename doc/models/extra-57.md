
# Extra 57

*This model accepts additional fields of type unknown.*

## Structure

`Extra57`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `amount` | `number` | Required | - |
| `maskedPan` | `string` | Required | - |
| `cardBrand` | `string` | Required | - |
| `cardIssuerCountry` | `string` | Required | - |
| `cardholderName` | `string` | Required | - |
| `expiryMonth` | `string \| undefined` | Optional | - |
| `cardIssuer` | `string \| undefined` | Optional | - |
| `cardType` | `string \| undefined` | Optional | - |
| `expiryYear` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Extra57 } from 'ps-apimatic-sdk';

const extra57: Extra57 = {
  amount: 10,
  maskedPan: 'VISA',
  cardBrand: 'VISA',
  cardIssuerCountry: 'VISA',
  cardholderName: 'Test user',
  expiryMonth: 'expiry_month8',
  cardIssuer: 'card_issuer4',
  cardType: 'card_type6',
  expiryYear: 'expiry_year6',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

