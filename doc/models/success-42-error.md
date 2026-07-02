
# Success 42 Error

*This model accepts additional fields of type unknown.*

## Structure

`Success42Error`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `data` | [`Data`](../../doc/models/data.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
try {
  // make the API call
} catch (error) {
  if (error instanceof Success42Error) {
    console.log(error.result);
  }
}
```

