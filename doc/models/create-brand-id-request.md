
# Create Brand Id Request

*This model accepts additional fields of type unknown.*

## Structure

`CreateBrandIdRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreateBrandIdRequest } from 'ps-apimatic-sdk';

const createBrandIdRequest: CreateBrandIdRequest = {
  name: 'Sample brand name1',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

