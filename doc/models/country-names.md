
# Country Names

*This model accepts additional fields of type unknown.*

## Structure

`CountryNames`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `any` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CountryNames } from 'ps-apimatic-sdk';

const countryNames: CountryNames = {
  any: 'Other',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

