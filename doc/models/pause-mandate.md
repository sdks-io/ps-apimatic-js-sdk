
# Pause Mandate

*This model accepts additional fields of type unknown.*

## Structure

`PauseMandate`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mandateId` | `string` | Required | - |
| `pauseEndDate` | `number` | Required | - |
| `message` | `string` | Required | - |
| `pauseStartDate` | `number` | Required | - |
| `status` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PauseMandate } from 'ps-apimatic-sdk';

const pauseMandate: PauseMandate = {
  mandateId: '693c053feef6a6b6928b48b0',
  pauseEndDate: 1769859769,
  message: 'Mandate paused configuration done successfully for the selected duration',
  pauseStartDate: 1769857969,
  status: 'PAUSED',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

