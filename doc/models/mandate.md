
# Mandate

*This model accepts additional fields of type unknown.*

## Structure

`Mandate`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mandateMaxAmount` | `string` | Required | - |
| `amountVariability` | `string` | Required | - |
| `startDate` | `string` | Required | - |
| `endDate` | `string` | Required | - |
| `frequency` | `string` | Required | - |
| `rule` | `string` | Required | - |
| `value` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Mandate } from 'ps-apimatic-sdk';

const mandate: Mandate = {
  mandateMaxAmount: '5000',
  amountVariability: 'Fixed',
  startDate: '1598965200',
  endDate: '1914141600',
  frequency: 'MONTHLY',
  rule: 'on',
  value: 1,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

