
# Revoke Mandate Request

*This model accepts additional fields of type unknown.*

## Structure

`RevokeMandateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mandateId` | `string` | Required | - |
| `command` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { RevokeMandateRequest } from 'ps-apimatic-sdk';

const revokeMandateRequest: RevokeMandateRequest = {
  mandateId: '685cc8515e3af922dd0e8c31',
  command: 'revoke',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

