
# Purchases Request 2

*This model accepts additional fields of type unknown.*

## Structure

`PurchasesRequest2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client` | [`Client24`](../../doc/models/client-24.md) | Required | - |
| `purchase` | [`Purchase10`](../../doc/models/purchase-10.md) | Required | - |
| `paymentMethod` | `string` | Required | - |
| `merchantRef` | `string` | Required | - |
| `brandId` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PurchasesRequest2 } from 'ps-apimatic-sdk';

const purchasesRequest2: PurchasesRequest2 = {
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
    taxNumber: '39933551809',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  purchase: {
    currency: 'BRL',
    products: [
      {
        name: 'test ',
        price: 10,
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      }
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  paymentMethod: 'PIX',
  merchantRef: 'test12',
  brandId: '90ed108b-6753-465d-8a21-e2cc604ff814',
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

