
# Payment Methods Error

*This model accepts additional fields of type unknown.*

## Structure

`PaymentMethodsError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `all` | [`All[]`](../../doc/models/all.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
try {
  // make the API call
} catch (error) {
  if (error instanceof PaymentMethodsError) {
    console.log(error.result);
  }
}
```

