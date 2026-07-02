# API

```ts
const api = new Api(client);
```

## Class Name

`Api`

## Methods

* [Partial Refund API](../../doc/controllers/api.md#partial-refund-api)
* [Partial Refund Status API](../../doc/controllers/api.md#partial-refund-status-api)


# Partial Refund API

## Refund Scenarios

### Partial Refund

Purchase Amount: 10

Refund Amount: 8

Result:

- Refunded Amount: 8

- Remaining Refundable Amount: 2

- Transaction Status: PARTIALLY_REFUNDED

Full Refund Using Partial Refund API

Purchase Amount: 10

Refund Amount: 10

Result:

- Refunded Amount: 10

- Remaining Refundable Amount: 0

- Transaction Status: PARTIAL REFUNDED

### Multiple Partial Refunds

Purchase Amount: 10

- Refund #1: 3

- Refund #2: 2

- Refund #3: 5

Result:

- Total Refunded Amount: 10

- Remaining Refundable Amount: 0

Final Transaction Status: PARTIAL REFUNDED

:information_source: **Note** This endpoint does not require authentication.

```ts
async partialRefundApi(
  accept: string,
  body: PartialRefundApiRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accept` | `string` | Header, Required | - |
| `body` | [`PartialRefundApiRequest`](../../doc/models/partial-refund-api-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const accept = '*/*';

const body: PartialRefundApiRequest = {
  amount: '5.12',
  reason: 'Partial Refunds Testing',
};

try {
  const response = await api.partialRefundApi(
    accept,
    body
  );

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
    if (error instanceof Success51Error) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | [`Success51Error`](../../doc/models/success-51-error.md) |


# Partial Refund Status API

:information_source: **Note** This endpoint does not require authentication.

```ts
async partialRefundStatusApi(
  body: PartialRefundStatusApiRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PartialRefundStatusApiRequest`](../../doc/models/partial-refund-status-api-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const body: PartialRefundStatusApiRequest = {
  refundId: 'refundid',
};

try {
  const response = await api.partialRefundStatusApi(body);

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
    if (error instanceof Success51Error) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | [`Success51Error`](../../doc/models/success-51-error.md) |

