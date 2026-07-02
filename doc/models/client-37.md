
# Client 37

*This model accepts additional fields of type unknown.*

## Structure

`Client37`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `string` | Required | - |
| `country` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `documentId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client37 } from 'ps-apimatic-sdk';

const client37: Client37 = {
  email: 'test@gmail.com',
  country: 'EG',
  phone: '9586445444',
  fullName: 'Test Person-uk',
  documentId: '29206260104051',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

