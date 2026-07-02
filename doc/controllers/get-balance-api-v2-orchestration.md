# Get Balance API V2-Orchestration

```ts
const getBalanceApiV2OrchestrationApi = new GetBalanceApiV2OrchestrationApi(client);
```

## Class Name

`GetBalanceApiV2OrchestrationApi`


# Checking Balance

## **API for checking available balance**

1. URL :- /getBalance/

2. RequestType: POST

3. Request Body

Note: Currency is not a mandatory parameter. If no parameter is specified then all respective currency balances would be provided, if any specific currency parameter is provided then only that currency balance would be provided.

:information_source: **Note** This endpoint does not require authentication.

```ts
async checkingBalance(
  body: CheckingBalanceRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<CheckingBalancePayoutSuccess2>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CheckingBalanceRequest`](../../doc/models/checking-balance-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`CheckingBalancePayoutSuccess2`](../../doc/models/checking-balance-payout-success-2.md).

## Example Usage

```ts
const body: CheckingBalanceRequest = {
  paymentMethod: 'PAYOUT-INTERAC-ETRANSFER',
};

try {
  const response = await getBalanceApiV2OrchestrationApi.checkingBalance(body);

  // Extracting fully parsed response body.
  console.log(response.result);

  // Extracting response status code.
  console.log(response.statusCode);
  // Extracting response headers.
  console.log(response.headers);
  // Extracting response body of type `string | Stream`
  console.log(response.body);
} catch (error) {
  if (error instanceof ApiError) {
    // Extracting response error status code.
    console.log(error.statusCode);
    // Extracting response error headers.
    console.log(error.headers);
    // Extracting response error body of type `string | Stream`.
    console.log(error.body);
  }
}
```

## Example Response *(as JSON)*

```json
{
  "paymentMethod": "PAYOUT-INTERAC-ETRANSFER",
  "status": "success",
  "gateways": [
    {
      "gatewayName": "payhost",
      "status": "success",
      "error": null,
      "balances": [
        {
          "currency": "CAD",
          "balance": 808.38
        },
        {
          "currency": "USD",
          "balance": 803.38
        }
      ]
    },
    {
      "gatewayName": "choicepaypg",
      "status": "success",
      "error": null,
      "balances": [
        {
          "currency": "CAD",
          "balance": 808.38
        },
        {
          "currency": "USD",
          "balance": 808.38
        }
      ]
    }
  ],
  "aggregatedBalances": [
    {
      "currency": "CAD",
      "balance": 1616.76
    },
    {
      "currency": "USD",
      "balance": 1611.76
    }
  ]
}
```

