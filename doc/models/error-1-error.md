
# Error 1 Error

*This model accepts additional fields of type unknown.*

## Structure

`Error1Error`

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
  if (error instanceof Error1Error) {
    console.log(error.result);
  }
}
```

