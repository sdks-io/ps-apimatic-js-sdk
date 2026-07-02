
# Trust Score Exists

*This model accepts additional fields of type unknown.*

## Structure

`TrustScoreExists`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `trustScore` | `number` | Required | - |
| `deliverable` | `string` | Required | - |
| `proxy` | `string` | Required | - |
| `vpn` | `string` | Required | - |
| `tor` | `string` | Required | - |
| `activeVpn` | `string` | Required | - |
| `activeTor` | `string` | Required | - |
| `recentAbuse` | `string` | Required | - |
| `botStatus` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { TrustScoreExists } from 'ps-apimatic-sdk';

const trustScoreExists: TrustScoreExists = {
  trustScore: 0,
  deliverable: 'false',
  proxy: 'false',
  vpn: 'false',
  tor: 'false',
  activeVpn: 'false',
  activeTor: 'false',
  recentAbuse: 'false',
  botStatus: 'false',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

