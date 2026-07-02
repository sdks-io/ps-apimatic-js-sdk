# Payout Manual Review

```ts
const payoutManualReviewApi = new PayoutManualReviewApi(client);
```

## Class Name

`PayoutManualReviewApi`

## Methods

* [List Payouts](../../doc/controllers/payout-manual-review.md#list-payouts)
* [Approve Payout](../../doc/controllers/payout-manual-review.md#approve-payout)
* [Approve Payout with Remarks](../../doc/controllers/payout-manual-review.md#approve-payout-with-remarks)
* [Reject Payout](../../doc/controllers/payout-manual-review.md#reject-payout)
* [Reject Payout with Remarks](../../doc/controllers/payout-manual-review.md#reject-payout-with-remarks)


# List Payouts

:information_source: **Note** This endpoint does not require authentication.

```ts
async listPayouts(
  pageNo: number,
  pageSize: number,
  status: string,
  timezone: string,
  startDate: string,
  endDate: string,
  paymentMethod: string,
  email: string,
  customerSegment: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `pageNo` | `number` | Query, Required | - |
| `pageSize` | `number` | Query, Required | - |
| `status` | `string` | Query, Required | - |
| `timezone` | `string` | Query, Required | - |
| `startDate` | `string` | Query, Required | - |
| `endDate` | `string` | Query, Required | - |
| `paymentMethod` | `string` | Query, Required | - |
| `email` | `string` | Query, Required | - |
| `customerSegment` | `string` | Query, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const pageNo = 1;

const pageSize = 10;

const status = 'error';

const timezone = 'Asia/Kolkata';

const startDate = '2025-01-01 00:00:00';

const endDate = '2026-04-27 00:00:00';

const paymentMethod = 'PAYOUT-SPEI, PAYOUT-INTERAC-ETRANSFER';

const email = 'testmail+2@gmail.com,%testmail+2669@gmail.com';

const customerSegment = 'NA';

try {
  const response = await payoutManualReviewApi.listPayouts(
    pageNo,
    pageSize,
    status,
    timezone,
    startDate,
    endDate,
    paymentMethod,
    email,
    customerSegment
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
  }
}
```


# Approve Payout

:information_source: **Note** This endpoint does not require authentication.

```ts
async approvePayout(
  action: string,
  body: unknown,
  payoutId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `action` | `string` | Query, Required | - |
| `body` | `unknown` | Body, Required | - |
| `payoutId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const action = 'approve';

const body = {  };

const payoutId = 'payout_id6';

try {
  const response = await payoutManualReviewApi.approvePayout(
    action,
    body,
    payoutId
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
  }
}
```


# Approve Payout with Remarks

:information_source: **Note** This endpoint does not require authentication.

```ts
async approvePayoutWithRemarks(
  action: string,
  body: ApprovePayoutWithRemarksRequest,
  payoutId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `action` | `string` | Query, Required | - |
| `body` | [`ApprovePayoutWithRemarksRequest`](../../doc/models/approve-payout-with-remarks-request.md) | Body, Required | - |
| `payoutId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const action = 'approve';

const body: ApprovePayoutWithRemarksRequest = {
  remarks: 'Verified against invoice #4821',
};

const payoutId = 'payout_id6';

try {
  const response = await payoutManualReviewApi.approvePayoutWithRemarks(
    action,
    body,
    payoutId
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
  }
}
```


# Reject Payout

:information_source: **Note** This endpoint does not require authentication.

```ts
async rejectPayout(
  action: string,
  body: unknown,
  payoutId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `action` | `string` | Query, Required | - |
| `body` | `unknown` | Body, Required | - |
| `payoutId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const action = 'reject';

const body = {  };

const payoutId = 'payout_id6';

try {
  const response = await payoutManualReviewApi.rejectPayout(
    action,
    body,
    payoutId
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
  }
}
```


# Reject Payout with Remarks

:information_source: **Note** This endpoint does not require authentication.

```ts
async rejectPayoutWithRemarks(
  action: string,
  body: RejectPayoutWithRemarksRequest,
  payoutId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `action` | `string` | Query, Required | - |
| `body` | [`RejectPayoutWithRemarksRequest`](../../doc/models/reject-payout-with-remarks-request.md) | Body, Required | - |
| `payoutId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const action = 'reject';

const body: RejectPayoutWithRemarksRequest = {
  remarks: 'Failed KYC verification',
};

const payoutId = 'payout_id6';

try {
  const response = await payoutManualReviewApi.rejectPayoutWithRemarks(
    action,
    body,
    payoutId
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
  }
}
```

