
# Success 12

*This model accepts additional fields of type unknown.*

## Structure

`Success12`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payoutId` | `string` | Required | - |
| `client` | [`Client46`](../../doc/models/client-46.md) | Required | - |
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
| `successRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `redirectType` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Success12 } from 'ps-apimatic-sdk';

const success12: Success12 = {
  payoutId: '683d778dc74d23074a56ea94',
  client: {
    customerId: 'NA',
    email: 'ashishm.21190@gmail.com',
    phone: '+14377717874',
    fullName: 'MARCO ANTONIO FERNANDEZ RAMIREZ',
    country: 'MX',
    speiClabe: '012180027944986155',
    stateCode: 'test',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1748858765,
  payoutMethod: 'PAYOUT-SPEI',
  amountUnit: 'MAJOR',
  amount: 20,
  errorMsg: '',
  purpose: 'test payout',
  createdOn: 1748858765,
  merchantRef: '683d778dc74d23074a56ea94',
  status: 'paid',
  statusHistory: [
    {
      status: 'created',
      timestamp: 1748858765,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      status: 'paid',
      timestamp: 1748858765,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  currency: 'MXN',
  paymentOn: 0,
  taxAmount: 0,
  taxPercent: 0,
  successRedirect: 'https://test.com/getResponse.jsp?success=true',
  failureRedirect: 'https://test.com/getResponse.jsp?success=false',
  redirectType: 'GET',
  successCallback: 'https://test1.com',
  failureCallback: 'https://test2.com',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

