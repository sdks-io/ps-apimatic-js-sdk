
# Extra Param 26

*This model accepts additional fields of type unknown.*

## Structure

`ExtraParam26`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `aft` | [`Aft`](../../doc/models/aft.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ExtraParam26 } from 'ps-apimatic-sdk';

const extraParam26: ExtraParam26 = {
  aft: {
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
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

