
# Create Pay Out Request 3

*This model accepts additional fields of type unknown.*

## Structure

`CreatePayOutRequest3`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client29`](../../doc/models/client-29.md) | Required | - |
| `purpose` | `string` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `currency` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreatePayOutRequest3 } from 'ps-apimatic-sdk';

const createPayOutRequest3: CreatePayOutRequest3 = {
  client: {
    email: 'test@gmail.com',
    fullName: 'test test',
    country: 'BR',
    city: 'Brasília',
    stateCode: 'SP',
    streetAddress: 'Praça da Bíblia 1308',
    zipCode: '57312-140',
    dateOfBirth: '1994-31-04',
    phone: '+558262362732',
    documentId: ' 97c1c590-554b-4449-a0f1-8da9f9756937',
    documentType: 'evp',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purpose: 'payout to test',
  payoutMethod: 'Payout-PIX',
  brandId: '{{merchant_brand_id}}',
  amount: 10,
  currency: 'BRL',
  successRedirect: 'https://test.com/getResponse.jsp?success=true',
  pendingRedirect: 'https://test.com/getResponse.jsp?success=pending',
  failureRedirect: 'https://test.com/getResponse.jsp?success=false',
  successCallback: 'https://test1.com',
  failureCallback: 'https://test2.com',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

