
# Client 46

*This model accepts additional fields of type unknown.*

## Structure

`Client46`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Required | - |
| `email` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `country` | `string` | Required | - |
| `speiClabe` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client46 } from 'ps-apimatic-sdk';

const client46: Client46 = {
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
};
```

