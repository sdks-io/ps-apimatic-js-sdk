
# Success 36 Error

*This model accepts additional fields of type unknown.*

## Structure

`Success36Error`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `string` | Required | - |
| `frequency` | `string` | Required | - |
| `rule` | `string` | Required | - |
| `value` | `number` | Required | - |
| `totalDeductedAmount` | `string` | Required | - |
| `recurringMandateIds` | `string[]` | Required | - |
| `email` | `string` | Required | - |
| `nextMandateDate` | `number` | Required | - |
| `customerId` | `string` | Required | - |
| `mandateId` | `string` | Required | - |
| `mandateMaxAmount` | `number` | Required | - |
| `amountVariability` | `string` | Required | - |
| `startDate` | `string` | Required | - |
| `endDate` | `string` | Required | - |
| `pauseStartDate` | `string` | Required | - |
| `pauseEndDate` | `string` | Required | - |
| `sessionId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
try {
  // make the API call
} catch (error) {
  if (error instanceof Success36Error) {
    console.log(error.result);
  }
}
```

