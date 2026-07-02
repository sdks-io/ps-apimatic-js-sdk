
# Aft

*This model accepts additional fields of type unknown.*

## Structure

`Aft`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accountOwnerAddress1` | `string` | Required | - |
| `accountOwnerAddress2` | `string` | Required | - |
| `accountOwnerStreet` | `string` | Required | - |
| `accountOwnerPostalCode` | `string` | Required | - |
| `accountOwnerCity` | `string` | Required | - |
| `accountOwnerCountry` | `string` | Required | - |
| `merchantPostalCode` | `string` | Required | - |
| `merchantState` | `string` | Required | - |
| `acceptorLegalName` | `string` | Required | - |
| `senderAddress` | `string` | Required | - |
| `senderCity` | `string` | Required | - |
| `senderState` | `string` | Required | - |
| `senderCountry` | `string` | Required | - |
| `senderName` | `string` | Required | - |
| `senderAccountNumber` | `string` | Required | - |
| `recipientName` | `string` | Required | - |
| `bai` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Aft } from 'ps-apimatic-sdk';

const aft: Aft = {
  accountOwnerAddress1: 'test',
  accountOwnerAddress2: 'test',
  accountOwnerStreet: 'test',
  accountOwnerPostalCode: '123',
  accountOwnerCity: 'test',
  accountOwnerCountry: 'UK',
  merchantPostalCode: '123',
  merchantState: 'FRA',
  acceptorLegalName: 'test',
  senderAddress: 'test',
  senderCity: 'test',
  senderState: 'RJ',
  senderCountry: 'FRA',
  senderName: 'test',
  senderAccountNumber: 'test',
  recipientName: 'test',
  bai: 'AA',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

