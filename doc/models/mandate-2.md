
# Mandate 2

*This model accepts additional fields of type unknown.*

## Structure

`Mandate2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `frequency` | `string` | Required | - |
| `rule` | `string` | Required | - |
| `value` | `string \| null` | Required | - |
| `mandateMaxAmount` | `string \| null` | Required | - |
| `amountVariability` | `string` | Required | - |
| `endDate` | `string \| null` | Required | - |
| `mandateStatus` | `string` | Required | - |
| `mandateId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Mandate2 } from 'ps-apimatic-sdk';

const mandate2: Mandate2 = {
  frequency: 'ASPRESENTED',
  rule: 'on',
  value: 'value6',
  mandateMaxAmount: 'mandate_max_amount0',
  amountVariability: 'Variable',
  endDate: 'end_date6',
  mandateStatus: 'CREATED',
  mandateId: '69f8d167db7ca561ab27c484',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

