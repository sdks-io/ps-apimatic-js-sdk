
# Success 44 Error

*This model accepts additional fields of type unknown.*

## Structure

`Success44Error`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `data` | [`Data2`](../../doc/models/data-2.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
try {
  // make the API call
} catch (error) {
  if (error instanceof Success44Error) {
    console.log(error.result);
  }
}
```

