
# Existing Customer Error

*This model accepts additional fields of type unknown.*

## Structure

`ExistingCustomerError`

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
  if (error instanceof ExistingCustomerError) {
    console.log(error.result);
  }
}
```

