
# Trust Score Error

*This model accepts additional fields of type unknown.*

## Structure

`TrustScoreError`

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
  if (error instanceof TrustScoreError) {
    console.log(error.result);
  }
}
```

