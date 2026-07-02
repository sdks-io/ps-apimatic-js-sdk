
# Payment Data

*This model accepts additional fields of type unknown.*

## Structure

`PaymentData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `onlinePaymentCryptogram` | `string` | Required | - |
| `eciIndicator` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PaymentData } from 'ps-apimatic-sdk';

const paymentData: PaymentData = {
  onlinePaymentCryptogram: 'AgAAAAAABk4D...',
  eciIndicator: '05',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

