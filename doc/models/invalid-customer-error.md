
# Invalid Customer Error

*This model accepts additional fields of type unknown.*

## Structure

`InvalidCustomerError`

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
  if (error instanceof InvalidCustomerError) {
    console.log(error.result);
  }
}
```

