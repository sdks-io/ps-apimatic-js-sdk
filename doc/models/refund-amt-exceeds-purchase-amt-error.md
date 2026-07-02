
# Refund Amt Exceeds Purchase Amt Error

*This model accepts additional fields of type unknown.*

## Structure

`RefundAmtExceedsPurchaseAmtError`

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
  if (error instanceof RefundAmtExceedsPurchaseAmtError) {
    console.log(error.result);
  }
}
```

