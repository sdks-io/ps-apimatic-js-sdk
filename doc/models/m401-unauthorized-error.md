
# M401 Unauthorized Error

*This model accepts additional fields of type unknown.*

## Structure

`M401UnauthorizedError`

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
  if (error instanceof M401UnauthorizedError) {
    console.log(error.result);
  }
}
```

