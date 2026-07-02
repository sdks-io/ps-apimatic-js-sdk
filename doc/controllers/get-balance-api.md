# Get Balance API

```ts
const getBalanceApi = new GetBalanceApi(client);
```

## Class Name

`GetBalanceApi`

## Methods

* [Checking Balance](../../doc/controllers/get-balance-api.md#checking-balance)
* [Checking Balance 1](../../doc/controllers/get-balance-api.md#checking-balance-1)
* [Checking Balance 2](../../doc/controllers/get-balance-api.md#checking-balance-2)
* [Checking Balance 3](../../doc/controllers/get-balance-api.md#checking-balance-3)


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
): Promise<ApiResponse<CheckingBalancePayoutSuccess>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CheckingBalanceRequest`](../../doc/models/checking-balance-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`CheckingBalancePayoutSuccess`](../../doc/models/checking-balance-payout-success.md).

## Example Usage

```ts
const body: CheckingBalanceRequest = {
  paymentMethod: 'INTERAC-ETRANSFER',
};

try {
  const response = await getBalanceApi.checkingBalance(body);

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
  "paymentMethod": "INTERAC-ETRANSFER",
  "status": "success",
  "data": [
    {
      "currency": "AUD",
      "balance": "0.00"
    },
    {
      "currency": "BRL",
      "balance": "0.00"
    },
    {
      "currency": "EUR",
      "balance": "0.00"
    },
    {
      "currency": "INR",
      "balance": "0.00"
    },
    {
      "currency": "JPY",
      "balance": "0.00"
    },
    {
      "currency": "USD",
      "balance": "0.00"
    }
  ]
}
```


# Checking Balance 1

## **API for Checking Balance payout**

1. URL :- /getBalance/

2. RequestType: POST

3. Request Body

Note: Currency is not a mandatory parameter. If no parameter is specified then all respective currency balances would be provided, if any specific currency parameter is provided then only that currency balance would be provided.

:information_source: **Note** This endpoint does not require authentication.

```ts
async checkingBalance1(
  body: CheckingBalanceRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success6>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CheckingBalanceRequest`](../../doc/models/checking-balance-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success6`](../../doc/models/success-6.md).

## Example Usage

```ts
const body: CheckingBalanceRequest = {
  paymentMethod: 'INTERAC-REQUEST-MONEY',
};

try {
  const response = await getBalanceApi.checkingBalance1(body);

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
  "currency": "CAD",
  "balance": "2.22",
  "paymentMethod": "INTERAC-REQUEST-MONEY",
  "status": "success"
}
```


# Checking Balance 2

## **API for Checking Balance payout**

1. URL :- /getBalance/

2. RequestType: POST

3. Request Body

Note: Currency is not a mandatory parameter. If no parameter is specified then all respective currency balances would be provided, if any specific currency parameter is provided then only that currency balance would be provided.

:information_source: **Note** This endpoint does not require authentication.

```ts
async checkingBalance2(
  body: CheckingBalanceRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<CheckingBalancePayoutSuccess>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CheckingBalanceRequest`](../../doc/models/checking-balance-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`CheckingBalancePayoutSuccess`](../../doc/models/checking-balance-payout-success.md).

## Example Usage

```ts
const body: CheckingBalanceRequest = {
  paymentMethod: 'INTERAC',
};

try {
  const response = await getBalanceApi.checkingBalance2(body);

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
  "paymentMethod": "FAWRYPAY",
  "status": "success",
  "data": [
    {
      "currency": "AUD",
      "balance": "0.00"
    },
    {
      "currency": "CAD",
      "balance": "0.00"
    },
    {
      "currency": "EGP",
      "balance": "-1.20"
    },
    {
      "currency": "EUR",
      "balance": "0.00"
    },
    {
      "currency": "GBP",
      "balance": "0.00"
    },
    {
      "currency": "INR",
      "balance": "0.00"
    },
    {
      "currency": "NGN",
      "balance": "0.00"
    },
    {
      "currency": "USD",
      "balance": "0.00"
    },
    {
      "currency": "ZAR",
      "balance": "0.00"
    }
  ]
}
```


# Checking Balance 3

## **API for Checking Balance payout**

1. URL :- /getBalance/

2. RequestType: POST

3. Request Body

Note: Currency is not a mandatory parameter. If no parameter is specified then all respective currency balances would be provided, if any specific currency parameter is provided then only that currency balance would be provided.

:information_source: **Note** This endpoint does not require authentication.

```ts
async checkingBalance3(
  body: CheckingBalanceRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success24>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CheckingBalanceRequest`](../../doc/models/checking-balance-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success24`](../../doc/models/success-24.md).

## Example Usage

```ts
const body: CheckingBalanceRequest = {
  paymentMethod: 'BANKTRANSFER',
};

try {
  const response = await getBalanceApi.checkingBalance3(body);

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
    if (error instanceof FailureError) {
      console.log(error.result);
    }
  }
}
```

## Example Response *(as JSON)*

```json
{
  "paymentMethod": "BANKTRANSFER",
  "status": "success",
  "data": [
    {
      "currency": "AUD",
      "balance": "0.00"
    },
    {
      "currency": "USD",
      "balance": "46813.79"
    },
    {
      "currency": "JPY",
      "balance": "1012.00"
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`FailureError`](../../doc/models/failure-error.md) |

