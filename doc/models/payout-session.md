
# Payout Session

*This model accepts additional fields of type unknown.*

## Structure

`PayoutSession`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sessionUrl` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `customerId` | `string` | Required | - |
| `sessionId` | `string` | Required | - |
| `expiryOn` | `number` | Required | - |
| `createdOn` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PayoutSession } from 'ps-apimatic-sdk';

const payoutSession: PayoutSession = {
  sessionUrl: 'https://staging.paysecure.net/payoutSession/68341e385f895955355d5671/',
  brandId: '{yourBrandID}',
  customerId: '67c9983fba18400ab6cceb8f',
  sessionId: '68341e385f895955355d5671',
  expiryOn: 1748246972,
  createdOn: 1748246072,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

