
# Transaction Already Refunded Error

*This model accepts additional fields of type unknown.*

## Structure

`TransactionAlreadyRefundedError`

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
  if (error instanceof TransactionAlreadyRefundedError) {
    console.log(error.result);
  }
}
```

