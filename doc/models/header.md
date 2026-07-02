
# Header

*This model accepts additional fields of type unknown.*

## Structure

`Header`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ephemeralPublicKey` | `string` | Required | - |
| `publicKeyHash` | `string` | Required | - |
| `transactionId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Header } from 'ps-apimatic-sdk';

const header: Header = {
  ephemeralPublicKey: '...',
  publicKeyHash: '...',
  transactionId: '...',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

