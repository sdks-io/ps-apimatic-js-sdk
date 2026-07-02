
# Success 21

*This model accepts additional fields of type unknown.*

## Structure

`Success21`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payoutId` | `string` | Required | - |
| `client` | [`Client80`](../../doc/models/client-80.md) | Required | - |
| `updatedOn` | `number` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `amountUnit` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `errorMsg` | `string` | Required | - |
| `purpose` | `string` | Required | - |
| `createdOn` | `number` | Required | - |
| `merchantRef` | `string` | Required | - |
| `status` | `string` | Required | - |
| `statusHistory` | [`StatusHistory[]`](../../doc/models/status-history.md) | Required | - |
| `currency` | `string` | Required | - |
| `paymentOn` | `number` | Required | - |
| `taxAmount` | `number` | Required | - |
| `taxPercent` | `number` | Required | - |
| `redirectType` | `string` | Required | - |
| `extraParam` | [`ExtraParam13`](../../doc/models/extra-param-13.md) | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success21 } from 'ps-apimatic-sdk';

const success21: Success21 = {
  payoutId: '685faaf0b93cc30dd78957c6',
  client: {
    customerId: '685fa7d7b93cc30dd78956c1',
    email: 'rahul+7@paysecure.net',
    phone: '+918839471520',
    fullName: 'Rahul Agarwal',
    streetAddress: 'Vaishali Jaipur',
    country: 'FR',
    city: 'jaipur',
    zipCode: '202020',
    stateCode: 'RA',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1751100145,
  payoutMethod: 'PAYOUT-VIRTUAL-CARDS',
  amountUnit: 'MAJOR',
  amount: 5,
  errorMsg: '',
  purpose: 'payout to test',
  createdOn: 1751100145,
  merchantRef: '685faaf0b93cc30dd78957c6',
  status: 'PAID',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1751100145,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'paid',
      timestamp: 1751100145,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  currency: 'EUR',
  paymentOn: 1751100145,
  taxAmount: 0,
  taxPercent: 0,
  redirectType: 'POST',
  extraParam: {
    productType: 'HOTAC',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  successCallback: 'https://success.com',
  failureCallback: 'https://failure.com',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

