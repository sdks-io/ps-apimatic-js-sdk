
# Pause Mandate Request

*This model accepts additional fields of type unknown.*

## Structure

`PauseMandateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mandateId` | `string` | Required | - |
| `command` | `string` | Required | - |
| `pauseStartDate` | `string` | Required | - |
| `pauseEndDate` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PauseMandateRequest } from 'ps-apimatic-sdk';

const pauseMandateRequest: PauseMandateRequest = {
  mandateId: '685cc8515e3af922dd0e8c31',
  command: 'pause',
  pauseStartDate: '1761985415',
  pauseEndDate: '1761985415',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

