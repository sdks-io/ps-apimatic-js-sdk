
# Refund Exceeds Remaining Balance after a Partial Refund Error

*This model accepts additional fields of type unknown.*

## Structure

`RefundExceedsRemainingBalanceAfterAPartialRefundError`

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
  if (error instanceof RefundExceedsRemainingBalanceAfterAPartialRefundError) {
    console.log(error.result);
  }
}
```

