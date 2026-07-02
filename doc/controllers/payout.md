# Payout

**API Flow**

<img src="https://lh7-us.googleusercontent.com/Uxy8jmp5RP-c360-oIMAZy2As8naqJdARgKsWU0x_BtszfJlwdRVM6-obffbtjTABfI9V0hxH4Ad-Ns96We42lIMdL434tTzLJ6aEQBt0dzX_ZXeM4RtG_kmEeem7WIsN520Zh5PS3xTFYNzOmks0ak">
1. The merchant initiates the payout via the create payout API. If successful, they will receive a paid status in the response. If any additional fields are required from the user, the status would be in pending and the user needs to be redirected to the checkout_url.

2. After a successful or failed payment by the end user, an appropriate webhook would be sent to the merchant. If the user would be redirected to the checkout_url for some additional details, once the user clicks on Pay, the user will be redirected to the appropriate redirect URL.

Available payout methods: PAYOUT-BANKTRANSFER

```ts
const payoutApi = new PayoutApi(client);
```

## Class Name

`PayoutApi`

## Methods

* [Pay Out](../../doc/controllers/payout.md#pay-out)
* [Get Status](../../doc/controllers/payout.md#get-status)
* [Create Pay Out](../../doc/controllers/payout.md#create-pay-out)
* [Get Status 1](../../doc/controllers/payout.md#get-status-1)


# Pay Out

To Initiate a payment, the very first API call to make is `/payout/` with the required data in the request body.

To generate a Payout, you are required to provide the `API key` (in the header) can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a Payout request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.email | The customer's email. |
| client.phone | The customer's phone number along with the country code.  <br>Example: +91 9634088651 |
| client.city | The customer's city. |
| client.country | ISO-3166 Country Code. Must be upper case. Example “SG” (Alpha2) |
| client.stateCode | Example “AL”, “XZ”. Must be in upper case. |
| Client.street_address | The customer's address. |
| client.zip_code | The customer's ZIP or postal code. If country=US, zip format must be NNNNN or NNNNN-NNNN. |
| currency | ISO 4217 code for currency you want to send the transaction in.  <br>  <br>Please note, the currency has to be enabled by the account manager for your account. |
| amount | amount in decimal format.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
| payoutMethod | example: PAYOUT-BANKTRANSFER |
| success_redirect | URL to send the user if the transactions is successful. |
| pending_redirect | URL to send the user if the transactions is in pending. |
| failure_redirect | URL to send the user if the transactions is unsuccessful. |
| Purpose | The purpose of doing a payout. |

### Additional **parameters for this usecase:**

| **Parameter** | **Notes** |
| --- | --- |
| beneficiaryDetail.bankName | The Bank Name in which the customer want's to credit the money.  <br>  <br>Optional Field.  <br>If passed, only use the mentioned bank names below. Anything else might lead to payout failures.  <br>If you don't want to pass, then you might need to open our checkout_url in the response and user can select the Bank from the dropdown. |
| beneficiaryDetail.bankAccountName | Mandatory Field.  <br>Account Holder's Full Name.  <br>It is advised to have atleast 2 words in the name. |
| beneficiaryDetail.bankAccountCurrency | Optional Field.  <br>The Currency in which the money will be credited. Generally the same as the `currency` field mentioned above. |
| beneficiaryDetail.bankAccountNumber | Mandatory Field.  <br>Account Holder's Account Number.  <br>This is the account in which the money will be credited. |
| beneficiaryDetail.ifscCode | Mandatory Field.  <br>IFSC code of the account in which the money will be credited. |
| beneficiaryDetail.bankCountryCode | Optional Field.  <br>The country code in which the account exist. Generally the same as the `country` field mentioned above. |

**Bank Names:**

<img src="https://content.pstmn.io/94f46e68-73b7-4a16-bff1-1d4a57dd6e92/aW1hZ2UucG5n" width="676" height="3498">


:information_source: **Note** This endpoint does not require authentication.

```ts
async payOut(
  accept: string,
  body: PayOutRequest1,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accept` | `string` | Header, Required | - |
| `body` | [`PayOutRequest1`](../../doc/models/pay-out-request-1.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const accept = 'application/json';

const body: PayOutRequest1 = {
  client: {
    email: 'customer141@gmail.com',
    streetAddress: 'Vaishali Nagar',
    city: 'Jaipur',
    fullName: 'Rahul Jain',
    zipCode: '302018',
    country: 'IN',
    stateCode: 'RJ',
    phone: '+91 9634088651',
  },
  beneficiaryDetail: {
    bankAccountName: 'Rahul Jain',
    bankAccountNumber: '123456789012',
    ifscCode: 'HDFC021212',
  },
  payoutMethod: 'Payout-BANKTRANSFER',
  brandId: '{{merchant_brand_id}}',
  amount: 100,
  currency: 'INR',
  purpose: 'payout for testing',
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
};

try {
  const response = await payoutApi.payOut(
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
  }
}
```

## Example Response

```
"{\r\n    \"payoutId\": \"6977137755e0628e3600c562\",\r\n    \"client\": {\r\n        \"customerId\": \"NA\",\r\n        \"email\": \"customer141@gmail.com\",\r\n        \"phone\": \"+91 9634088651\",\r\n        \"country\": \"IN\",\r\n        \"zip_code\": \"302018\",\r\n        \"city\": \"Jaipur\",\r\n        \"street_address\": \"Vaishali Nagar\",\r\n        \"full_name\": \"Rahul Jain\",\r\n        \"stateCode\": \"RJ\"\r\n    },\r\n    \"updated_on\": 1769411447,\r\n    \"payoutMethod\": \"PAYOUT-BANKTRANSFER\",\r\n    \"beneficiaryDetail\": {\r\n        \"bankAccountName\": \"Rahul Jain\",\r\n        \"bankAccountNumber\": \"123456789012\",\r\n        \"ifscCode\": \"HDFC021212\"\r\n    },\r\n    \"amountUnit\": \"MAJOR\",\r\n    \"amount\": 100.0,\r\n    \"errorMsg\": \"\",\r\n    \"purpose\": \"payout for testing\",\r\n    \"created_on\": 1769411447,\r\n    \"merchantRef\": \"6977137755e0628e3600c562\",\r\n    \"status\": \"PAID\",\r\n    \"status_history\": [\r\n        {\r\n            \"status\": \"created\",\r\n            \"timestamp\": 1769411447\r\n        },\r\n        {\r\n            \"status\": \"paid\",\r\n            \"timestamp\": 1769411447\r\n        },\r\n\r\n    ],\r\n    \"currency\": \"INR\",\r\n    \"extraFee\": \"0\",\r\n    \"paymentOn\": 0,\r\n    \"checkout_url\": \"https://test4.paymentsclub.net/payout/092e59f94279a3742fa3715fe9a2112a/\",\r\n    \"taxAmount\": 0.0,\r\n    \"taxPercent\": 0.0,\r\n    \"success_redirect\": \"https://your.success.redirect.com\",\r\n    \"pending_redirect\": \"https://your.pending.redirect.com\",\r\n    \"failure_redirect\": \"https://your.failure.redirect.com\",\r\n    \"success_callback\": \"https://your.success.callback.com\",\r\n    \"failure_callback\": \"https://your.failure.callback.com\"\r\n    \"redirectType\": \"POST\",\r\n    \"sessionId\": \"\",\r\n    \"surcharge\": 0.0,\r\n    \"surchargeType\": \"\",\r\n    \"trxMethod\": \"BANKTRANSFER\",\r\n    \"success_callback\": \"\",\r\n    \"failure_callback\": \"\"\r\n}"
```


# Get Status

This API tells you about all the details of a Payout, including its history.

### Mandatory

you need to pass the payoutId in the API URL

### Possible Value of Status

| **Status** | **Notes** |
| --- | --- |
| paid | Transaction Successful |
| payout_in_process | payout is under Processing. |
| error | Transaction has Failed. |

:information_source: **Note** This endpoint does not require authentication.

```ts
async getStatus(
  payoutId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payoutId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const payoutId = 'payoutId4';

try {
  const response = await payoutApi.getStatus(payoutId);

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

## Example Response

```
"{\r\n    \"payoutId\": \"6977137755e0628e3600c562\",\r\n    \"client\": {\r\n        \"customerId\": \"NA\",\r\n        \"email\": \"customer141@gmail.com\",\r\n        \"phone\": \"+91 9634088651\",\r\n        \"country\": \"IN\",\r\n        \"zip_code\": \"302018\",\r\n        \"city\": \"Jaipur\",\r\n        \"street_address\": \"Vaishali Nagar\",\r\n        \"full_name\": \"Rahul Jain\",\r\n        \"stateCode\": \"RJ\"\r\n    },\r\n    \"updated_on\": 1769411447,\r\n    \"payoutMethod\": \"PAYOUT-BANKTRANSFER\",\r\n    \"beneficiaryDetail\": {\r\n        \"bankAccountName\": \"Rahul Jain\",\r\n        \"bankAccountNumber\": \"123456789012\",\r\n        \"ifscCode\": \"HDFC021212\"\r\n    },\r\n    \"amountUnit\": \"MAJOR\",\r\n    \"amount\": 100.0,\r\n    \"errorMsg\": \"\",\r\n    \"purpose\": \"payout for testing\",\r\n    \"created_on\": 1769411447,\r\n    \"merchantRef\": \"6977137755e0628e3600c562\",\r\n    \"status\": \"PAID\",\r\n    \"status_history\": [\r\n        {\r\n            \"status\": \"created\",\r\n            \"timestamp\": 1769411447\r\n        },\r\n        {\r\n            \"status\": \"paid\",\r\n            \"timestamp\": 1769411447\r\n        },\r\n\r\n    ],\r\n    \"currency\": \"INR\",\r\n    \"extraFee\": \"0\",\r\n    \"paymentOn\": 0,\r\n    \"checkout_url\": \"https://test4.paymentsclub.net/payout/092e59f94279a3742fa3715fe9a2112a/\",\r\n    \"taxAmount\": 0.0,\r\n    \"taxPercent\": 0.0,\r\n    \"success_redirect\": \"https://your.success.redirect.com\",\r\n    \"pending_redirect\": \"https://your.pending.redirect.com\",\r\n    \"failure_redirect\": \"https://your.failure.redirect.com\",\r\n    \"success_callback\": \"https://your.success.callback.com\",\r\n    \"failure_callback\": \"https://your.failure.callback.com\"\r\n    \"redirectType\": \"POST\",\r\n    \"sessionId\": \"\",\r\n    \"surcharge\": 0.0,\r\n    \"surchargeType\": \"\",\r\n    \"trxMethod\": \"BANKTRANSFER\",\r\n    \"success_callback\": \"\",\r\n    \"failure_callback\": \"\"\r\n}"
```


# Create Pay Out

To Initiate a payment, the very first call to make is `/payout/` with the required data in the request body.

To generate a Payout, you are required to provide the `API key` (in the header) can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a Payout request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.email | An Identifier for a user |
| client.phone | An Identifier for a user |
| client.full_name | An Identifier for a user |
| client.country |  |
| payoutMethod | PAYOUT-THIRDPARTY-UPI |
| beneficiaryDetail.upi | VPA (UPI ID) |
| Currency | Note this is currency account for which you have balance |
| Amount | Amount in Currency |
| Purpose | Purpose of the payment |

:information_source: **Note** This endpoint does not require authentication.

```ts
async createPayOut(
  body: CreatePayOutRequest7,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreatePayOutRequest7`](../../doc/models/create-pay-out-request-7.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const body: CreatePayOutRequest7 = {
  client: {
    email: 'yogesh@gmail.com',
    country: 'CA',
    phone: '766225230591',
    fullName: 'Test Person-uk',
  },
  beneficiaryDetail: {
    upi: 'alpha@bravo',
  },
  purpose: 'test payout',
  currency: 'INR',
  payoutMethod: 'PAYOUT-THIRDPARTY-UPI',
  amount: 10,
  successCallback: 'https://success.com',
  failureCallback: 'https://failure.com',
};

try {
  const response = await payoutApi.createPayOut(body);

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


# Get Status 1

This API tells you about all the details of a Payout, including its history

### Mandatory

you need to pass the payoutId in the API URL

### Possible Value of Status

| **Status** | **Notes** |
| --- | --- |
| paid | Transaction Successful |
| payout_in_process | payout is under Processing. |
| error | Transaction has Failed. |

The webhook will only be triggered for paid transactions or errors.

Paid: "success_callback": "[https://success.com](https://success.com)",

Error: "failure_callback": “[https://failure.com”](https://failure.com”)

:information_source: **Note** This endpoint does not require authentication.

```ts
async getStatus1(
  payoutId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<GetSuccessStatus3>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payoutId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`GetSuccessStatus3`](../../doc/models/get-success-status-3.md).

## Example Usage

```ts
const payoutId = 'payoutId4';

try {
  const response = await payoutApi.getStatus1(payoutId);

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
  "payoutId": "66838ae86d41e41c10a8656d",
  "client": {
    "email": "Yogesh@gmail.com",
    "phone": "766533230591",
    "full_name": "Test Person-uk",
    "country": "CA"
  },
  "updated_on": 1719896808,
  "payoutMethod": "PAYOUT-UPI",
  "beneficiaryDetail": {
    "upi": "charles.babbage@okhdfc",
    "transferType": "UPI"
  },
  "amountUnit": "MAJOR",
  "amount": 10.0,
  "errorMsg": "",
  "purpose": "test payout",
  "created_on": 1719896808,
  "merchantRef": "66838ae86d41e41c10a8656d",
  "merchantName": "newMerchant777",
  "status": "PAYOUT_IN_PROCESS",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1719896808
    },
    {
      "status": "payout_in_process",
      "timestamp": 1719896810
    },
    {
      "status": "viewed",
      "timestamp": 1719900796
    }
  ],
  "viewedOn": 1719900796,
  "currency": "INR",
  "paymentOn": 0,
  "success_callback": "https://success.com",
  "failure_callback": "https://failure.com"
}
```

