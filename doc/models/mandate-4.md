
# Mandate 4

*This model accepts additional fields of type unknown.*

## Structure

`Mandate4`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `string` | Required | - |
| `frequency` | `string` | Required | - |
| `rule` | `string` | Required | - |
| `value` | `number` | Required | - |
| `totalDeductedAmount` | `string` | Required | - |
| `recurringMandateIds` | `string[] \| undefined` | Optional | - |
| `email` | `string` | Required | - |
| `nextMandateDate` | `number \| undefined` | Optional | - |
| `customerId` | `string` | Required | - |
| `mandateId` | `string` | Required | - |
| `mandateMaxAmount` | `number` | Required | - |
| `amountVariability` | `string` | Required | - |
| `startDate` | `string` | Required | - |
| `sessionId` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Mandate4 } from 'ps-apimatic-sdk';

const mandate4: Mandate4 = {
  status: 'ACTIVE',
  frequency: 'WEEKLY',
  rule: 'after',
  value: 4,
  totalDeductedAmount: '10.00',
  email: 'test@gmail.com',
  customerId: '696bd627b0c24568ade4675e',
  mandateId: '696bc39a7bc779fac5201357',
  mandateMaxAmount: 120,
  amountVariability: 'Variable',
  startDate: '1768670106',
  recurringMandateIds: [
    '6973ad04fa54ee2cf14f438c',
    '697ce750e6446c7babfe4727'
  ],
  nextMandateDate: 1770398106,
  sessionId: 'session_id4',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

