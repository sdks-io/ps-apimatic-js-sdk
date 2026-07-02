# Transaction Reporting

```ts
const transactionReportingApi = new TransactionReportingApi(client);
```

## Class Name

`TransactionReportingApi`

## Methods

* [List Transactions](../../doc/controllers/transaction-reporting.md#list-transactions)
* [Get Detailed Transaction Details](../../doc/controllers/transaction-reporting.md#get-detailed-transaction-details)


# List Transactions

Fetches a paginated list of transactions. This endpoint is optimized for high-volume retrieval and returns a summary view of each transaction (ID and Status).

#### **Important Path Params to consider:**

| **Fields** | **Description** |
| --- | --- |
| page_no | The index number of the page to retrieve.  <br>Zero-based indexing: The first page is 0, the second is 1, etc.  <br>Example: To get the third page of results, send page_no=2 |
| page_size | The number of records to return per page.  <br>Minimum: 1  <br>Maximum: 100 (or whatever your API limit is).  <br>Usage: A larger page_size reduces the number of API calls but increases payload size. |
| transaction_id | If you want to filter with a specific transaction id. Multiple ids are not supported.  <br>If a transaction id is passed, it has the highest priority. All the below mentioned filters are ommitted. |
| start_date | If you want to filter between 2 dates.  <br>Format: 2026-01-07 16:12:00 +05:30  <br>Base timezone is in UTC. |
| end_date | If you want to filter between 2 dates  <br>Format: 2026-01-07 16:12:00 +05:30  <br>Base timezone is in UTC. |
| last_updated_start | If you want to filter with the last updated date of a transaction.  <br>Format: 2026-01-07 16:12:00 +05:30  <br>Base timezone is in UTC. |
| last_updated_end | If you want to filter with the last updated date of a transaction.  <br>Format: 2026-01-07 16:12:00 +05:30  <br>Base timezone is in UTC. |
| customer_id | If you want to filter with a specific customer id. Multiple ids are not supported. |
| status | If you want to filter with the status. |
| currency | If you want to filter with the currency. |

:information_source: **Note** This endpoint does not require authentication.

```ts
async listTransactions(
  pageNo: number,
  pageSize: number,
  transactionId: string,
  startDate: string,
  endDate: string,
  lastUpdatedStart: string,
  lastUpdatedEnd: string,
  customerId: string,
  status: string,
  currency: string,
  isSandbox: boolean,
  brandId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `pageNo` | `number` | Query, Required | - |
| `pageSize` | `number` | Query, Required | - |
| `transactionId` | `string` | Query, Required | - |
| `startDate` | `string` | Query, Required | - |
| `endDate` | `string` | Query, Required | - |
| `lastUpdatedStart` | `string` | Query, Required | - |
| `lastUpdatedEnd` | `string` | Query, Required | - |
| `customerId` | `string` | Query, Required | - |
| `status` | `string` | Query, Required | - |
| `currency` | `string` | Query, Required | - |
| `isSandbox` | `boolean` | Query, Required | - |
| `brandId` | `string` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const pageNo = 1;

const pageSize = 10;

const transactionId = '69d4ba22465443878a0045ba';

const startDate = '2025-10-29 00:00:00 +05:30';

const endDate = '2026-04-23 00:00:00 +05:30';

const lastUpdatedStart = '2026-01-07 16:12:00 +05:30';

const lastUpdatedEnd = '2026-12-07 16:12:00 +05:30';

const customerId = 'NA';

const status = 'paid';

const currency = 'USD';

const isSandbox = true;

const brandId = 'your-brand-id';

try {
  const response = await transactionReportingApi.listTransactions(
    pageNo,
    pageSize,
    transactionId,
    startDate,
    endDate,
    lastUpdatedStart,
    lastUpdatedEnd,
    customerId,
    status,
    currency,
    isSandbox,
    brandId
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
    if (error instanceof Success42Error) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`Success42Error`](../../doc/models/success-42-error.md) |


# Get Detailed Transaction Details

Retrieves the complete details for a specific transaction. This includes customer info, payment method details, bank response codes, and hierarchy metadata (parent/child transactions).

### Additional query **parameters for this usecase:**

| **Parameter** | **Notes** |
| --- | --- |
| include_subtransactions | Mandatory.  <br>Possible Values: true/false  <br>  <br>If true, includes child transactions (e.g., recurring payments). |

:information_source: **Note** This endpoint does not require authentication.

```ts
async getDetailedTransactionDetails(
  pageNo: number,
  pageSize: number,
  includeSubtransactions: boolean,
  brandId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `pageNo` | `number` | Query, Required | - |
| `pageSize` | `number` | Query, Required | - |
| `includeSubtransactions` | `boolean` | Query, Required | - |
| `brandId` | `string` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const pageNo = 1;

const pageSize = 10;

const includeSubtransactions = true;

const brandId = 'your-brand-id';

try {
  const response = await transactionReportingApi.getDetailedTransactionDetails(
    pageNo,
    pageSize,
    includeSubtransactions,
    brandId
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
    if (error instanceof Success44Error) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`Success44Error`](../../doc/models/success-44-error.md) |

