
# Requiredinput

*This model accepts additional fields of type unknown.*

## Structure

`Requiredinput`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ip` | `string` | Required | - |
| `email` | `string` | Required | - |
| `url` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Requiredinput } from 'ps-apimatic-sdk';

const requiredinput: Requiredinput = {
  ip: '111.11.11.11',
  email: 'test@gmail.com',
  url: 'https://www.asos.com/',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

