
# Refund on an Already Refunded Purchase Error

*This model accepts additional fields of type unknown.*

## Structure

`RefundOnAnAlreadyRefundedPurchaseError`

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
  if (error instanceof RefundOnAnAlreadyRefundedPurchaseError) {
    console.log(error.result);
  }
}
```

