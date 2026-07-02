
# Success 40

*This model accepts additional fields of type unknown.*

## Structure

`Success40`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mandates` | [`Mandate4[]`](../../doc/models/mandate-4.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success40 } from 'ps-apimatic-sdk';

const success40: Success40 = {
  mandates: [
    {
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
    },
    {
      status: 'CREATED',
      frequency: 'WEEKLY',
      rule: 'on',
      value: 6,
      totalDeductedAmount: '0',
      email: 'test@gmail.com',
      customerId: '696bd627b0c24568ade4675e',
      mandateId: '696bd627b0c24568ade4675e',
      mandateMaxAmount: 120,
      amountVariability: 'Variable',
      startDate: '1768674855',
      recurringMandateIds: [
        'recurringMandateIds0',
        'recurringMandateIds1'
      ],
      nextMandateDate: 128,
      sessionId: '',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'ACTIVE',
      frequency: 'WEEKLY',
      rule: 'after',
      value: 4,
      totalDeductedAmount: '0',
      email: 'test@gmail.com',
      customerId: '696bd627b0c24568ade4675e',
      mandateId: '69788a5dd1ed27eeb5fb89d6',
      mandateMaxAmount: 120,
      amountVariability: 'Variable',
      startDate: '1769507493',
      recurringMandateIds: [
        'recurringMandateIds0',
        'recurringMandateIds1'
      ],
      nextMandateDate: 128,
      sessionId: '',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'ACTIVE',
      frequency: 'WEEKLY',
      rule: 'after',
      value: 4,
      totalDeductedAmount: '1000',
      email: 'test@gmail.com',
      customerId: '696bd627b0c24568ade4675e',
      mandateId: '69788d2f0ea4df4fd4e6eb5b',
      mandateMaxAmount: 120,
      amountVariability: 'Variable',
      startDate: '1769508214',
      recurringMandateIds: [
        '6973ad04fa54ee2cf14f438c',
        '697ce750e6446c7babfe4727'
      ],
      nextMandateDate: 128,
      sessionId: '',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'FAILED',
      frequency: 'WEEKLY',
      rule: 'after',
      value: 4,
      totalDeductedAmount: '0',
      email: 'test@gmail.com',
      customerId: '696bd627b0c24568ade4675e',
      mandateId: '697b533b34d180d90cfb2f5f',
      mandateMaxAmount: 120,
      amountVariability: 'Variable',
      startDate: '1769689915',
      recurringMandateIds: [
        'recurringMandateIds0',
        'recurringMandateIds1'
      ],
      nextMandateDate: 128,
      sessionId: '',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'CREATED',
      frequency: 'WEEKLY',
      rule: 'after',
      value: 4,
      totalDeductedAmount: '0',
      email: 'test@gmail.com',
      customerId: '696bd627b0c24568ade4675e',
      mandateId: '697de0e15d2e562bf8b4552a',
      mandateMaxAmount: 120,
      amountVariability: 'Variable',
      startDate: '1769857249',
      recurringMandateIds: [
        'recurringMandateIds0',
        'recurringMandateIds1'
      ],
      nextMandateDate: 128,
      sessionId: '',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

