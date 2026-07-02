
# Request Global Account Request

*This model accepts additional fields of type unknown.*

## Structure

`RequestGlobalAccountRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `country` | `string` | Required | - |
| `currency` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { RequestGlobalAccountRequest } from 'ps-apimatic-sdk';

const requestGlobalAccountRequest: RequestGlobalAccountRequest = {
  country: 'AE',
  currency: 'AED',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

