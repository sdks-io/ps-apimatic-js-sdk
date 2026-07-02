
# Success 51 Error

*This model accepts additional fields of type unknown.*

## Structure

`Success51Error`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `refundId` | `string` | Required | - |
| `purchaseId` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `createdOn` | `number` | Required | - |
| `refundOn` | `number` | Required | - |
| `status` | `string` | Required | - |
| `reason` | `string` | Required | - |
| `currency` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
try {
  // make the API call
} catch (error) {
  if (error instanceof Success51Error) {
    console.log(error.result);
  }
}
```

