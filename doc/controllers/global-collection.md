# Global Collection

```ts
const globalCollectionApi = new GlobalCollectionApi(client);
```

## Class Name

`GlobalCollectionApi`

## Methods

* [Get Merchants](../../doc/controllers/global-collection.md#get-merchants)
* [Delete Merchant API](../../doc/controllers/global-collection.md#delete-merchant-api)
* [Create Merchant API](../../doc/controllers/global-collection.md#create-merchant-api)
* [Update Merchant](../../doc/controllers/global-collection.md#update-merchant)
* [Create Merchant API Token](../../doc/controllers/global-collection.md#create-merchant-api-token)
* [Get Single Merchant](../../doc/controllers/global-collection.md#get-single-merchant)
* [Get Missing Invoice Transactions](../../doc/controllers/global-collection.md#get-missing-invoice-transactions)
* [Get Settlement Data](../../doc/controllers/global-collection.md#get-settlement-data)
* [Delete Merchant Token](../../doc/controllers/global-collection.md#delete-merchant-token)
* [Create Brand ID](../../doc/controllers/global-collection.md#create-brand-id)
* [Delete Brand ID](../../doc/controllers/global-collection.md#delete-brand-id)
* [Request Global Account](../../doc/controllers/global-collection.md#request-global-account)
* [Get Global Accounts](../../doc/controllers/global-collection.md#get-global-accounts)
* [Bulk Update Invoice No](../../doc/controllers/global-collection.md#bulk-update-invoice-no)


# Get Merchants

```ts
async getMerchants(
  page: number,
  size: number,
  requestId: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<GetMerchants>>
```

## Authentication

This endpoint requires [bearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `page` | `number` | Query, Required | - |
| `size` | `number` | Query, Required | - |
| `requestId` | `number` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`GetMerchants`](../../doc/models/get-merchants.md).

## Example Usage

```ts
const page = 1;

const size = 30;

const requestId = 12344;

try {
  const response = await globalCollectionApi.getMerchants(
    page,
    size,
    requestId
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

## Example Response *(as JSON)*

```json
{
  "status": "success",
  "data": {
    "merchant": [
      {
        "merchantId": 4143,
        "email": "test3@paysecure.co",
        "name": "Test Prithvi Merchants",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3451",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+912212345678",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "Asia/Kolkata",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": false,
        "allowedPaymentMethods": [
          "MASTER",
          "VISA",
          "JCB"
        ],
        "allowedCurrencies": []
      },
      {
        "merchantId": 4187,
        "email": "test10@paysecure.co",
        "name": "testprithvimerchant10",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3451",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP"
        ]
      },
      {
        "merchantId": 4256,
        "email": "test101@paysecure.co",
        "name": "testprithvimerchant101",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3451",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP",
          "USD"
        ]
      },
      {
        "merchantId": 4263,
        "email": "test1071@paysecure.co",
        "name": "testprithvimerchant1012",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3451",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP",
          "USD"
        ]
      },
      {
        "merchantId": 4274,
        "email": "test147dnh@paysecure.co",
        "name": "testprithvimerchant10d12",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3453",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": true,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP",
          "USD"
        ]
      },
      {
        "merchantId": 4270,
        "email": "test147dh@paysecure.co",
        "name": "testprithvimerchant10s12",
        "legalName": "Test Prithvirajtest Merchants Pvt Ltd",
        "regNo": "CIN12345678909",
        "websiteUrl": "https://testprithvi1.com",
        "category": "3451",
        "iecNo": "fdsjfk1shf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai1",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra1",
        "tradingPostal": "400011",
        "corporateAddress": "456 Corporate Avenue, Mumbai1",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400012",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap1",
        "officerTitle": "Director1",
        "officerName": "Prithvi Kashyap1",
        "defaultCurrency": "EUR",
        "defaultTimezone": "UTC",
        "allowGlobalCollection": true,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP"
        ]
      },
      {
        "merchantId": 4189,
        "email": "test11@paysecure.co",
        "name": "testprithvimerchant11",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3451",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP"
        ]
      },
      {
        "merchantId": 4195,
        "email": "test12@paysecure.co",
        "name": "testprithvimerchant12",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3451",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP"
        ]
      },
      {
        "merchantId": 4377,
        "email": "test1323e5hf2k@paysecure.co",
        "name": "testprithvimerchant12349",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3471",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "USD",
          "INR"
        ]
      },
      {
        "merchantId": 4196,
        "email": "test13@paysecure.co",
        "name": "testprithvimerchant13",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3451",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP",
          "USD"
        ]
      },
      {
        "merchantId": 4376,
        "email": "test1325hf2k@paysecure.co",
        "name": "testprithvimerchant13149",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3471",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "USD",
          "INR"
        ]
      },
      {
        "merchantId": 4197,
        "email": "test14@paysecure.co",
        "name": "testprithvimerchant14",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3451",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP",
          "USD"
        ]
      },
      {
        "merchantId": 4368,
        "email": "test1325j2k@paysecure.co",
        "name": "testprithvimerchant14249",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3471",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": false,
        "allowedPaymentMethods": [
          "CREDITCARD"
        ],
        "allowedCurrencies": []
      },
      {
        "merchantId": 4212,
        "email": "test15@paysecure.co",
        "name": "testprithvimerchant15",
        "legalName": "Test Prithvirajtest2 Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3451",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "UTC",
        "allowGlobalCollection": true,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "AED",
          "GBP"
        ]
      },
      {
        "merchantId": 4213,
        "email": "test16@paysecure.co",
        "name": "testprithvimerchant16",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3451",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP",
          "USD"
        ]
      },
      {
        "merchantId": 4230,
        "email": "test17@paysecure.co",
        "name": "testprithvimerchant17",
        "legalName": "Test Prithvirajtest2 Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3451",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "UTC",
        "allowGlobalCollection": true,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "AED",
          "GBP"
        ]
      },
      {
        "merchantId": 4288,
        "email": "test17as@paysecure.co",
        "name": "testprithvimerchant171",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3451",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP",
          "USD"
        ]
      },
      {
        "merchantId": 4382,
        "email": "test13wd3ehf2k@paysecure.co",
        "name": "testprithvimerchant2141",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3471",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "USD",
          "INR"
        ]
      },
      {
        "merchantId": 4293,
        "email": "test1711as@paysecure.co",
        "name": "testprithvimerchant217",
        "legalName": "Test Prithvirajtest2 Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3451",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "UTC",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "AED",
          "GBP"
        ]
      },
      {
        "merchantId": 4296,
        "email": "test1711sk@paysecure.co",
        "name": "testprithvimerchant219",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3451",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP",
          "USD"
        ]
      },
      {
        "merchantId": 4311,
        "email": "test1711smjk@paysecure.co",
        "name": "testprithvimerchant2198",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3471",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP",
          "USD"
        ]
      },
      {
        "merchantId": 4313,
        "email": "test17114smjk@paysecure.co",
        "name": "testprithvimerchant2199",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3471",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP",
          "USD"
        ]
      },
      {
        "merchantId": 4319,
        "email": "test17114smj1k@paysecure.co",
        "name": "testprithvimerchant2200",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3471",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP",
          "USD"
        ]
      },
      {
        "merchantId": 4322,
        "email": "test1711o4smj1k@paysecure.co",
        "name": "testprithvimerchant2201",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3471",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP",
          "USD"
        ]
      },
      {
        "merchantId": 4324,
        "email": "test1711osmj1k@paysecure.co",
        "name": "testprithvimerchant2202",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3471",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP",
          "USD"
        ]
      },
      {
        "merchantId": 4325,
        "email": "test1711psmj1k@paysecure.co",
        "name": "testprithvimerchant2203",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3471",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP",
          "USD"
        ]
      },
      {
        "merchantId": 4328,
        "email": "test1711psmj2k@paysecure.co",
        "name": "testprithvimerchant2204",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3471",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "GBP",
          "USD"
        ]
      },
      {
        "merchantId": 4335,
        "email": "test1711pgmj2k@paysecure.co",
        "name": "testprithvimerchant2205",
        "legalName": "Test Prithvirajtest2 Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3471",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "UTC",
        "allowGlobalCollection": true,
        "isLiveTransactionAllowed": true,
        "allowedPaymentMethods": [
          "PayByBank"
        ],
        "allowedCurrencies": [
          "AED",
          "GBP"
        ]
      },
      {
        "merchantId": 4354,
        "email": "test171pg5j2k@paysecure.co",
        "name": "testprithvimerchant2206",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3471",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": false,
        "allowedPaymentMethods": [
          "CREDITCARD"
        ],
        "allowedCurrencies": []
      },
      {
        "merchantId": 4355,
        "email": "test171p1g5j2k@paysecure.co",
        "name": "testprithvimerchant2207",
        "legalName": "Test Prithvi Merchants Pvt Ltd",
        "regNo": "CIN123456789",
        "websiteUrl": "https://testprithvi.com",
        "category": "3471",
        "iecNo": "fdsfkshf",
        "tradingStartDate": "2022-01-01",
        "dateOfIncorporation": "2021-06-15",
        "tradingAddress": "123 Trading Street, Mumbai",
        "tradingCountry": "IN",
        "tradingState": "Maharashtra",
        "tradingPostal": "400001",
        "corporateAddress": "456 Corporate Avenue, Mumbai",
        "corporateCountry": "IN",
        "corporateState": "Maharashtra",
        "corporatePostal": "400002",
        "businessPhone": "+912212345678",
        "contactPhone": "+919876543210",
        "contactName": "Prithvi Kashyap",
        "officerTitle": "Director",
        "officerName": "Prithvi Kashyap",
        "defaultCurrency": "EUR",
        "defaultTimezone": "EUR",
        "allowGlobalCollection": false,
        "isLiveTransactionAllowed": false,
        "allowedPaymentMethods": [
          "CREDITCARD"
        ],
        "allowedCurrencies": []
      }
    ],
    "pagination": {
      "currentPage": 1,
      "pageSize": 30,
      "totalElements": 44,
      "totalPages": 2,
      "first": true,
      "last": false,
      "hasNext": true,
      "hasPrevious": false
    }
  },
  "message": "Merchants fetched successfully",
  "reqId": "12344"
}
```


# Delete Merchant API

```ts
async deleteMerchantApi(
  merchantId: number,
  requestId: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DeleteMerchantApi>>
```

## Authentication

This endpoint requires [bearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `number` | Query, Required | - |
| `requestId` | `number` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DeleteMerchantApi`](../../doc/models/delete-merchant-api.md).

## Example Usage

```ts
const merchantId = 4229;

const requestId = 123;

try {
  const response = await globalCollectionApi.deleteMerchantApi(
    merchantId,
    requestId
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

## Example Response *(as JSON)*

```json
{
  "status": "success",
  "data": {
    "merchantId": 4388,
    "username": "testprithvimerchant18",
    "email": "test18@paysecure.co"
  },
  "message": "Merchant deleted successfully",
  "reqId": "123"
}
```


# Create Merchant API

```ts
async createMerchantApi(
  requestId: string,
  body: CreateMerchantApiRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<CreateMerchantApi>>
```

## Authentication

This endpoint requires [bearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestId` | `string` | Header, Required | - |
| `body` | [`CreateMerchantApiRequest`](../../doc/models/create-merchant-api-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`CreateMerchantApi`](../../doc/models/create-merchant-api.md).

## Example Usage

```ts
const requestId = 'abcd';

const body: CreateMerchantApiRequest = {
  username: 'testprithvimerchant17',
  mcc: 3451,
  iecNo: 'fdsfkshf',
  allowGlobalCollection: true,
  legalName: 'Test Prithvi Merchants Pvt Ltd',
  name: 'Test Prithvi Merchants 2',
  regNo: 'CIN123456789',
  emailId: 'test17@paysecure.co',
  websiteUrl: 'https://testprithvi.com',
  tradingStartDate: '2022-01-01',
  dateOfIncorporation: '2021-06-15',
  tradingAddress: '123 Trading Street, Mumbai',
  tradingCountry: 'IN',
  tradingState: 'Maharashtra',
  tradingPostal: '400001',
  corporateAddress: '456 Corporate Avenue, Mumbai',
  corporateCountry: 'IN',
  corporateState: 'Maharashtra',
  corporatePostal: '400002',
  businessPhone: '+912212345678',
  contactPhone: '+919876543210',
  contactName: 'Prithvi Kashyap',
  officerTitle: 'Director',
  officerName: 'Prithvi Kashyap',
  defaultCurrency: 'EUR',
  defaultTimezone: 'UTC',
  allowedPaymentMethods: [
    'PayByBank'
  ],
  allowedCurrencies: [
    'GBP',
    'USD'
  ],
  isLiveTransactionAllowed: true,
};

try {
  const response = await globalCollectionApi.createMerchantApi(
    requestId,
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
  }
}
```

## Example Response *(as JSON)*

```json
{
  "status": "success",
  "data": {
    "merchantId": 4389,
    "username": "testprithvimerchant18",
    "email": "test18@paysecure.co"
  },
  "message": "Merchant created successfully",
  "reqId": "abcd"
}
```


# Update Merchant

```ts
async updateMerchant(
  requestId: number,
  body: UpdateMerchantRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UpdateMerchant>>
```

## Authentication

This endpoint requires [bearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestId` | `number` | Header, Required | - |
| `body` | [`UpdateMerchantRequest`](../../doc/models/update-merchant-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UpdateMerchant`](../../doc/models/update-merchant.md).

## Example Usage

```ts
const requestId = 123;

const body: UpdateMerchantRequest = {
  legalName: 'Test Prithvirajtest2 Merchants Pvt Ltd',
  regNo: 'CIN123456789',
  websiteUrl: 'https://testprithvi.com',
  iecNo: 'fdsfkshf',
  tradingStartDate: '2022-01-01',
  dateOfIncorporation: '2021-06-15',
  tradingAddress: '123 Trading Street, Mumbai',
  tradingCountry: 'IN',
  tradingState: 'Maharashtra',
  tradingPostal: '400001',
  corporateAddress: '456 Corporate Avenue, Mumbai',
  corporateCountry: 'IN',
  corporateState: 'Maharashtra',
  corporatePostal: '400002',
  businessPhone: '+912212345678',
  contactPhone: '+919876543210',
  contactName: 'Prithvi Kashyap',
  officerTitle: 'Director',
  officerName: 'Prithvi Kashyap',
  defaultCurrency: 'EUR',
  defaultTimezone: 'UTC',
  allowedPaymentMethods: [
    'PayByBank'
  ],
  allowedCurrencies: [
    'GBP',
    'AED'
  ],
  isLiveTransactionAllowed: true,
};

try {
  const response = await globalCollectionApi.updateMerchant(
    requestId,
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
  }
}
```

## Example Response *(as JSON)*

```json
{
  "status": "success",
  "data": {
    "merchantId": 4389
  },
  "message": "Merchant details updated successfully",
  "reqId": "123"
}
```


# Create Merchant API Token

```ts
async createMerchantApiToken(
  requestId: string,
  body: CreateMerchantApiTokenRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<CreateMerchantApiToken>>
```

## Authentication

This endpoint requires [bearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestId` | `string` | Header, Required | - |
| `body` | [`CreateMerchantApiTokenRequest`](../../doc/models/create-merchant-api-token-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`CreateMerchantApiToken`](../../doc/models/create-merchant-api-token.md).

## Example Usage

```ts
const requestId = 'abcd';

const body: CreateMerchantApiTokenRequest = {
  apiLabel: 'testlabel18',
  isSandbox: false,
};

try {
  const response = await globalCollectionApi.createMerchantApiToken(
    requestId,
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
  }
}
```

## Example Response *(as JSON)*

```json
{
  "status": "success",
  "data": {
    "merchantId": 4389,
    "apiKey": "baf09d9df4bfae6af3db9901bb22ab235b8eb8104f6c45f97570104c31b1cd4c",
    "isSandbox": false
  },
  "message": "Merchant token generated successfully",
  "reqId": "abcd"
}
```


# Get Single Merchant

```ts
async getSingleMerchant(
  requestId: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<GetSingleMerchant>>
```

## Authentication

This endpoint requires [bearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestId` | `number` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`GetSingleMerchant`](../../doc/models/get-single-merchant.md).

## Example Usage

```ts
const requestId = 123456;

try {
  const response = await globalCollectionApi.getSingleMerchant(requestId);

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
  "status": "success",
  "data": {
    "merchantId": 4230,
    "email": "test17@paysecure.co",
    "name": "testprithvimerchant17",
    "legalName": "Test Prithvirajtest2 Merchants Pvt Ltd",
    "regNo": "CIN123456789",
    "websiteUrl": "https://testprithvi.com",
    "category": "3451",
    "iecNo": "fdsfkshf",
    "tradingStartDate": "2022-01-01",
    "dateOfIncorporation": "2021-06-15",
    "tradingAddress": "123 Trading Street, Mumbai",
    "tradingCountry": "IN",
    "tradingState": "Maharashtra",
    "tradingPostal": "400001",
    "corporateAddress": "456 Corporate Avenue, Mumbai",
    "corporateCountry": "IN",
    "corporateState": "Maharashtra",
    "corporatePostal": "400002",
    "businessPhone": "+912212345678",
    "contactPhone": "+919876543210",
    "contactName": "Prithvi Kashyap",
    "officerTitle": "Director",
    "officerName": "Prithvi Kashyap",
    "defaultCurrency": "EUR",
    "defaultTimezone": "UTC",
    "allowGlobalCollection": true,
    "isLiveTransactionAllowed": true,
    "allowedPaymentMethods": [
      "PayByBank"
    ],
    "allowedCurrencies": [
      "AED",
      "GBP"
    ]
  },
  "message": "Merchant details fetched successfully",
  "reqId": "123456"
}
```


# Get Missing Invoice Transactions

```ts
async getMissingInvoiceTransactions(
  page: number,
  size: number,
  requestId: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<GetMissingInvoiceTransactions>>
```

## Authentication

This endpoint requires [bearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `page` | `number` | Query, Required | - |
| `size` | `number` | Query, Required | - |
| `requestId` | `number` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`GetMissingInvoiceTransactions`](../../doc/models/get-missing-invoice-transactions.md).

## Example Usage

```ts
const page = 1;

const size = 4;

const requestId = 123456;

try {
  const response = await globalCollectionApi.getMissingInvoiceTransactions(
    page,
    size,
    requestId
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

## Example Response *(as JSON)*

```json
{
  "status": "success",
  "data": {
    "transactions": [
      {
        "transactionId": "69d79150aa6d618c9b4e5da1",
        "amount": 1,
        "currency": "GBP",
        "createdDate": 1775735120
      },
      {
        "transactionId": "69d627aafbb9070a716e284b",
        "amount": 1,
        "currency": "GBP",
        "createdDate": 1775642538
      },
      {
        "transactionId": "69d6277afbb9070a716e252b",
        "amount": 1,
        "currency": "GBP",
        "createdDate": 1775642490
      },
      {
        "transactionId": "69cced964235594c815952fc",
        "amount": 1,
        "currency": "GBP",
        "createdDate": 1775037848
      }
    ],
    "pagination": {
      "currentPage": 1,
      "pageSize": 4,
      "totalElements": 6,
      "totalPages": 2,
      "first": true,
      "last": false,
      "hasNext": true,
      "hasPrevious": false
    }
  },
  "message": "Missing invoice transactions fetched successfully",
  "reqId": "123456"
}
```


# Get Settlement Data

```ts
async getSettlementData(
  fromDate: string,
  toDate: string,
  status: string,
  pageNo: number,
  size: number,
  requestId: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<GetSettlementData>>
```

## Authentication

This endpoint requires [bearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `fromDate` | `string` | Query, Required | - |
| `toDate` | `string` | Query, Required | - |
| `status` | `string` | Query, Required | - |
| `pageNo` | `number` | Query, Required | - |
| `size` | `number` | Query, Required | - |
| `requestId` | `number` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`GetSettlementData`](../../doc/models/get-settlement-data.md).

## Example Usage

```ts
const fromDate = '2025-01-01';

const toDate = '2026-01-01';

const status = 'settled';

const pageNo = 1;

const size = 10;

const requestId = 123456;

try {
  const response = await globalCollectionApi.getSettlementData(
    fromDate,
    toDate,
    status,
    pageNo,
    size,
    requestId
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

## Example Response *(as JSON)*

```json
{
  "status": "success",
  "data": {
    "settlements": [
      {
        "settlementId": "1234",
        "amount": 100,
        "currency": "USD",
        "status": "settled",
        "settledOn": -41795
      },
      {
        "settlementId": "5678",
        "amount": 100,
        "currency": "USD",
        "status": "settled",
        "settledOn": -41795
      }
    ],
    "pagination": {
      "currentPage": 1,
      "pageSize": 2,
      "totalElements": 2,
      "totalPages": 1,
      "first": true,
      "last": true,
      "hasNext": false,
      "hasPrevious": false
    }
  },
  "reqId": "123456"
}
```


# Delete Merchant Token

```ts
async deleteMerchantToken(
  token: string,
  requestId: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DeleteMerchantToken>>
```

## Authentication

This endpoint requires [bearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | - |
| `requestId` | `number` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DeleteMerchantToken`](../../doc/models/delete-merchant-token.md).

## Example Usage

```ts
const token = '0382c1e93f579d2da9a93d1e1bdfe6781b81335f8501e7551e9f64404caf38e4';

const requestId = 123;

try {
  const response = await globalCollectionApi.deleteMerchantToken(
    token,
    requestId
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

## Example Response *(as JSON)*

```json
{
  "status": "success",
  "data": {
    "merchantId": 4389,
    "username": "testprithvimerchant18",
    "email": null
  },
  "message": "Merchant token deleted successfully",
  "reqId": "123"
}
```


# Create Brand ID

```ts
async createBrandId(
  requestId: number,
  body: CreateBrandIdRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<CreateBrandId>>
```

## Authentication

This endpoint requires [bearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestId` | `number` | Header, Required | - |
| `body` | [`CreateBrandIdRequest`](../../doc/models/create-brand-id-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`CreateBrandId`](../../doc/models/create-brand-id.md).

## Example Usage

```ts
const requestId = 123;

const body: CreateBrandIdRequest = {
  name: 'Sample brand name1',
};

try {
  const response = await globalCollectionApi.createBrandId(
    requestId,
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
  }
}
```

## Example Response *(as JSON)*

```json
{
  "status": "success",
  "data": {
    "id": 1000077,
    "name": "Sample brand name2",
    "brandId": "1d01b37c-bd35-4727-85f9-f0b1448dad67",
    "merchantId": 4230
  },
  "message": "Brand created successfully",
  "reqId": "123"
}
```


# Delete Brand ID

```ts
async deleteBrandId(
  brandId: string,
  requestId: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DeleteBrandId>>
```

## Authentication

This endpoint requires [bearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `brandId` | `string` | Query, Required | - |
| `requestId` | `number` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DeleteBrandId`](../../doc/models/delete-brand-id.md).

## Example Usage

```ts
const brandId = 'c2e82dfa-b074-49fe-8e1e-2f2d2c22fefc';

const requestId = 123;

try {
  const response = await globalCollectionApi.deleteBrandId(
    brandId,
    requestId
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

## Example Response *(as JSON)*

```json
{
  "status": "success",
  "data": {
    "id": 1000077,
    "name": "Sample brand name2",
    "brandId": "1d01b37c-bd35-4727-85f9-f0b1448dad67",
    "merchantId": 4230
  },
  "message": "Brand deleted successfully",
  "reqId": "123"
}
```


# Request Global Account

```ts
async requestGlobalAccount(
  requestId: number,
  body: RequestGlobalAccountRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<RequestGlobalAccount>>
```

## Authentication

This endpoint requires [bearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestId` | `number` | Header, Required | - |
| `body` | [`RequestGlobalAccountRequest`](../../doc/models/request-global-account-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`RequestGlobalAccount`](../../doc/models/request-global-account.md).

## Example Usage

```ts
const requestId = 12331;

const body: RequestGlobalAccountRequest = {
  country: 'AE',
  currency: 'AED',
};

try {
  const response = await globalCollectionApi.requestGlobalAccount(
    requestId,
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
  }
}
```

## Example Response *(as JSON)*

```json
{
  "status": "success",
  "data": {
    "country": "AE",
    "currency": "GBP",
    "status": "pending",
    "accountNo": "GC-AE-GBP-20260506-980-CED9D5",
    "createdOn": 1778074623
  },
  "message": "Global account request submitted"
}
```


# Get Global Accounts

```ts
async getGlobalAccounts(
  requestId: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<GetGlobalAccounts>>
```

## Authentication

This endpoint requires [bearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestId` | `number` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`GetGlobalAccounts`](../../doc/models/get-global-accounts.md).

## Example Usage

```ts
const requestId = 12331;

try {
  const response = await globalCollectionApi.getGlobalAccounts(requestId);

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
  "status": "success",
  "data": [
    {
      "country": "FR",
      "currency": "GBP",
      "status": "pending",
      "accountNo": "GC-FR-GBP-20260409-980-FE2004",
      "createdOn": 1775732111
    },
    {
      "country": "AE",
      "currency": "AED",
      "status": "active",
      "accountNo": "GC-AE-AED-20260504-980-54FA8D",
      "createdOn": 1777887002
    },
    {
      "country": "AE",
      "currency": "GBP",
      "status": "pending",
      "accountNo": "GC-AE-GBP-20260506-980-CED9D5",
      "createdOn": 1778074623
    }
  ],
  "message": "Global collection fetched successfully",
  "reqId": "12331"
}
```


# Bulk Update Invoice No

```ts
async bulkUpdateInvoiceNo(
  requestId: string,
  body: BulkUpdateInvoiceNoRequest[],
  requestOptions?: RequestOptions
): Promise<ApiResponse<BulkUpdateInvoiceNo>>
```

## Authentication

This endpoint requires [bearer](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestId` | `string` | Header, Required | - |
| `body` | [`BulkUpdateInvoiceNoRequest[]`](../../doc/models/bulk-update-invoice-no-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`BulkUpdateInvoiceNo`](../../doc/models/bulk-update-invoice-no.md).

## Example Usage

```ts
const requestId = 'abcd';

const body: BulkUpdateInvoiceNoRequest[] = [
  {
    transactionId: '69cceeba4235594c8159559f',
    invoiceNo: 'inv123',
  },
  {
    transactionId: 'temp',
    invoiceNo: 'inv123',
  }
];

try {
  const response = await globalCollectionApi.bulkUpdateInvoiceNo(
    requestId,
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
  }
}
```

## Example Response *(as JSON)*

```json
{
  "status": "success",
  "data": {
    "updatedCount": 1,
    "skippedTransactionIds": [
      "temp"
    ]
  },
  "message": "Bulk invoice update completed",
  "reqId": "abcd"
}
```

