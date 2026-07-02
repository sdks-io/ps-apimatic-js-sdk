
# Refund Amt Is 0 or Ve Error

*This model accepts additional fields of type unknown.*

## Structure

`RefundAmtIs0OrVeError`

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
  if (error instanceof RefundAmtIs0OrVeError) {
    console.log(error.result);
  }
}
```

