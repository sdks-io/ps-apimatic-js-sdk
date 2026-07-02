
# M400 Bad Request Error

*This model accepts additional fields of type unknown.*

## Structure

`M400BadRequestError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `code` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
try {
  // make the API call
} catch (error) {
  if (error instanceof M400BadRequestError) {
    console.log(error.result);
  }
}
```

