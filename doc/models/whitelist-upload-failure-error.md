
# Whitelist Upload Failure Error

*This model accepts additional fields of type unknown.*

## Structure

`WhitelistUploadFailureError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message` | `string` | Required | - |
| `code` | `string` | Required | - |
| `status` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
try {
  // make the API call
} catch (error) {
  if (error instanceof WhitelistUploadFailureError) {
    console.log(error.result);
  }
}
```

