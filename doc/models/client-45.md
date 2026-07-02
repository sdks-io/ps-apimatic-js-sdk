
# Client 45

*This model accepts additional fields of type unknown.*

## Structure

`Client45`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `email` | `string` | Required | - |
| `country` | `string` | Required | - |
| `phone` | `string` | Required | - |
| `fullName` | `string` | Required | - |
| `stateCode` | `string` | Required | - |
| `speiClabe` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Client45 } from 'ps-apimatic-sdk';

const client45: Client45 = {
  email: 'ashishm.21190@gmail.com',
  country: 'MX',
  phone: '+14377717874',
  fullName: 'MARCO ANTONIO FERNANDEZ RAMIREZ',
  stateCode: 'test',
  speiClabe: '012180027944986158',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

