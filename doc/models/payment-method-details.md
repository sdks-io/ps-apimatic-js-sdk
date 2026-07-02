
# Payment Method Details

*This model accepts additional fields of type unknown.*

## Structure

`PaymentMethodDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `pan` | `string` | Required | - |
| `expirationMonth` | `number` | Required | - |
| `expirationYear` | `number` | Required | - |
| `authMethod` | `string` | Required | - |
| `cryptogram` | `string` | Required | - |
| `eciIndicator` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PaymentMethodDetails } from 'ps-apimatic-sdk';

const paymentMethodDetails: PaymentMethodDetails = {
  pan: '4111111111111111',
  expirationMonth: 12,
  expirationYear: 2027,
  authMethod: 'CRYPTOGRAM_3DS',
  cryptogram: 'AgAAAAAABk4D...',
  eciIndicator: '05',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

