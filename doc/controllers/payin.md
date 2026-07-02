# Payin

```ts
const payinApi = new PayinApi(client);
```

## Class Name

`PayinApi`

## Methods

* [Create Purchase](../../doc/controllers/payin.md#create-purchase)
* [Get Status](../../doc/controllers/payin.md#get-status)
* [Create Purchase 1](../../doc/controllers/payin.md#create-purchase-1)
* [Get Status 1](../../doc/controllers/payin.md#get-status-1)


# Create Purchase

### **Payin APIs**

<img src="https://content.pstmn.io/e448df41-3cb5-4b2a-9dc5-f961d9048bff/dW5uYW1lZC0yLnBuZw==" alt="" height="301" width="800">
**Integration Steps:** To integrate Virtual Account payments with Paysecure, follow these steps:

1. **Enable Virtual Account in Paysecure**: Sign up with Paysecure and ensure the Virtual Account payment method is enabled for your merchant account. Get your API keys for authentication (test and live).

2. **Configure Webhooks**: Set up Paysecure webhooks (e.g. transaction.paid, transaction.failed) so your system is notified of payment status changes.

3. **Implement PayIn** (Customer Payments): In your checkout flow, allow the customer to choose Virtual Account and then call Paysecure’s PayIn API (e.g. POST /purchases ) with parameters such as amount, currency and paymentMethod=VIRTUAL-ACCOUNT. To generate a Purchase, you are required to provide the Brand ID (in the request body) and API key (in the header). Both can be located in the Dashboard section of your merchant account login.

:information_source: **Note** This endpoint does not require authentication.

```ts
async createPurchase(
  body: CreatePurchaseRequest1,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PurchaseSucess>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreatePurchaseRequest1`](../../doc/models/create-purchase-request-1.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchaseSucess`](../../doc/models/purchase-sucess.md).

## Example Usage

```ts
const body: CreatePurchaseRequest1 = {
  client: {
    email: 'seo2009@test.com',
    streetAddress: '10 New Burlington Street Apt. 214',
    city: 'Sydney',
    fullName: 'Test test',
    zipCode: 'W1S 3BE',
    country: 'KR',
    dateOfBirth: '1970-07-10',
    stateCode: 'QLD',
    phone: '+447755564318',
  },
  purchase: {
    currency: 'KRW',
    products: [
      {
        name: 'test',
        price: 100,
      }
    ],
  },
  paymentMethod: 'VIRTUAL-ACCOUNT',
  brandId: 'f6aff7d7-bb40-4857-bc84-9b4c8310b043',
  successRedirect: 'https://your.success.redirect.url',
  pendingRedirect: 'https://your.pending.redirect.url',
  failureRedirect: 'https://your.failure.redirect.url',
  successCallback: 'https://your.success.callback.url',
  failureCallback: 'https://your.failure.callback.url',
};

try {
  const response = await payinApi.createPurchase(body);

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
  "purchaseId": "68441c2a7559cf659fd7e835",
  "client": {
    "customerId": "NA",
    "email": "arun44@gmail.com",
    "phone": "+237679544810",
    "full_name": "Olive Tsafack",
    "street_address": "test test",
    "country": "KR",
    "city": "123",
    "zip_code": "234567",
    "cc": [],
    "bcc": [],
    "stateCode": "ca"
  },
  "updated_on": 1749294123,
  "type": "purchase",
  "paymentMethod": "VIRTUAL-ACCOUNT",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "redirectType": "POST",
  "force_recurring": false,
  "created_on": 1749294123,
  "merchantRef": "68441c2a7559cf659fd7e835",
  "merchantName": "Merchant002",
  "purchase": {
    "currency": "KRW",
    "products": [
      {
        "name": "test",
        "quantity": 1,
        "price": 100,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 100,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1,
    "taxAmount": 0,
    "taxPercent": 0,
    "request_client_details": [],
    "timezone": "MIT",
    "email_message": ""
  },
  "issuer_details": {
    "website": "",
    "legal_street_address": "",
    "legal_country": "",
    "legal_city": "",
    "legal_zip_code": "",
    "bank_accounts": [
      {}
    ],
    "legal_name": "44",
    "brand_name": "44",
    "registration_number": "",
    "tax_number": ""
  },
  "transaction_data": {
    "payment_method": "",
    "flow": "payform",
    "extra": {},
    "country": "",
    "attempts": []
  },
  "status": "CREATED",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1749294123
    }
  ],
  "is_test": false,
  "brand_id": "c4003b2c-22d4-4dc1-ad0c-c6b54f8c9636",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS19963",
  "issued": "2025-06-07",
  "due": 1749294123,
  "refund_upto": 0,
  "cc_descriptor": "",
  "fraudScore": "NA",
  "trustScore": "NA",
  "paidOn": 0,
  "refund_availability": "NONE",
  "refundable_amount": 0,
  "success_redirect": "https://your.success.redirect.url",
  "pending_redirect": "https://your.pending.redirect.url",
  "failure_redirect": "https://your.failure.redirect.url",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.url",
  "failure_callback": "https://your.failure.callback.url",
  "platform": "API",
  "created_from_ip": "183.83.54.51",
  "checkout_url": "https://staging.paysecure.net/payments/68441c2a7559cf659fd7e835/",
  "payoutProcess": false
}
```


# Get Status

This API tells you about all the details of a purchase (PayIn), including its history

**Note:** With respect to bank transfers, the purchase request is synonymous with the PayIn request.

### Mandatory

you need to pass the `PurchaseID` in the API URL

### Possible Value of Status

| **Status** | **Notes** |
| --- | --- |
| paid | Transaction Successful |
| payment_in_process | Payment is under Processing |
| expired | Purchase has Expired. |
| error | Transaction has Failed. |

### Response Examples

In the response examples you can see instances of both `Paid` and `Error` Status purchases.

### Error Details

If there are any issues on the Purchase you can get more details from the `transaction_data.attempts.error` attribute of the response object

### Errors

If there are any errors then it'll be in the format of :

```json
{
    "message": "descriptive error message",
    "code": "error_code"
}

```

Please see the Status Code section for further details.

:information_source: **Note** This endpoint does not require authentication.

```ts
async getStatus(
  purchaseId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const purchaseId = 'purchaseId2';

try {
  const response = await payinApi.getStatus(purchaseId);

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
"{\r\n    \"purchaseId\": \"65f95faa70fe897720c40a15\",\r\n    \"client\": {\r\n----\r\n       },\r\n    \"updated_on\": 1710841770,\r\n    \"type\": \"purchase\",\r\n    \"amountUnit\": \"MAJOR\",\r\n    \"errorMsg\": \"\",\r\n    \"redirectType\": \"POST\",\r\n    \"force_recurring\": false,\r\n    \"created_on\": 1710841770,\r\n    \"merchantRef\": \"65f95faa70fe897720c40a15\",\r\n    \"merchantName\": \"test\",\r\n    \"purchase\": {\r\n----\r\n    },\r\n    \"issuer_details\": {\r\n-----\r\n    },\r\n    \"transaction_data\": {\r\n----\r\n    },\r\n    \"status\": \"CREATED\",\r\n    \"status_history\": [\r\n        {\r\n            \"status\": \"created\",\r\n            \"timestamp\": 1710841770\r\n        }\r\n    ],\r\n    \"is_test\": false,\r\n    \"brand_id\": \"90ed108b-6753-465d-8a21-e2cc604ff814\",\r\n    \"send_receipt\": false,\r\n    \"is_recurring_token\": false,\r\n    \"skip_capture\": false,\r\n    \"reference_generated\": \"PS2697\",\r\n    \"issued\": \"2024-03-19\",\r\n    \"due\": 1710841770,\r\n    \"refund_upto\": 0,\r\n    \"cc_descriptor\": \"\",\r\n    \"fraudScore\": \"NA\",\r\n    \"trustScore\": \"NA\",\r\n    \"refund_availability\": \"NONE\",\r\n    \"refundable_amount\": 0.0,\r\n    \"paymentMethod\" : \"BANKTRANSFER\",\r\n    \"brand_id\": \"90ed108b-6753-465d-8a21-e2cc604ff814 \",\r\n    \"success_redirect\": \"https://test.com/getResponse.jsp?success=true\",\r\n    \"failure_redirect\": \"https://test.com/getResponse.jsp?success=false\",\r\n    \"success_callback\": \"https://test1.com\",\r\n    \"failure_callback\": \"https://test2.com\"\r\n    \"cancel_redirect\": \"\",\r\n    \"platform\": \"API\",\r\n    \"created_from_ip\": \"110.235.229.223\",\r\n    \"checkout_url\": \"https://app.paysecure.net/payments/65f95faa70fe897720c40a15/\"\r\n}\r\n"
```


# Create Purchase 1

To Initiate a payment, the very first call to make is `/purchases` with the required data in the request body.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.email | An Identifier for a user |
| client.city |  |
| client.country | ISO-3166 Country Code. It must be upper case.  <br>This should be "IN" for India |
| client.stateCode | Example “AL”, “XZ”.. Must be in upper case. |
| client.street_address |  |
| client.zip_code |  |
| client.full_name |  |
| purchase.currency | ISO 4217 code for currency you want to send the transaction in. |
| purchase.products.name |  |
| purchase.products.price | Price in decimal format.  <br>example 1:  <br>INR 5 , should be sent as 10.00 |
| brand_id | Obtain from Dashboard section of your merchant account login. |
| success_redirect | URL to send the user if the transactions is successful |
| failure_redirect | URL to send the user if the transactions is UNSUCCESSFUL |

## Optional Parameters

### expireInMin

This parameter, when passed in the PayIn request, sets the time window within which a customer should make the Interac payment through their bank's app. If a customer doesn't complete the payment within the configured time window, the status of the payment will be marked as 'EXPIRED' in Paysecure.

However, in certain cases, a payment made outside of this window could still be successful i.e. customer's account may be debited which would result in inconsistencies among Paysecure's, merchant's and customer's status of the transaction. To avoid such cases it is advised to set the expiry time limit appropriately and advise the customers to make payment within this window. However, if there is an inconsistency between the status at Paysecure and at customer's Bank, the merchant and Paysecure will reconcile the amounts during the settlement.

### merchantRef

The `merchantRef` parameter, although not mandatory, is strongly advised for merchants to specify. Its inclusion offers two significant advantages for the merchant:

1. **Prevention of Duplicate Requests:** When a `merchantRef` is utilized, it acts as a unique identifier. This means that if a second purchase request is made using the same `merchantRef` (reference number), the system will recognize it and prevent duplicate transactions from occurring. This prevents unintended or duplicate purchases.

2. **Facilitation of Transaction Retrieval:** In situations where the response from the initial purchase request times out or the 'purchaseId' isn't received, having the `merchantRef` allows the merchant to retrieve detailed transaction information. This ensures they can track and access the specific purchase details related to that reference, even if the immediate response was not received.

However, if the merchant does not specify the 'merchantRef' parameter, the platform will automatically assign and use an internal 'purchaseId' as a reference for that transaction.

### paymentMethod

The `paymentMethod` parameter identifies which payment solution merchant wants to use to perform a transaction. If parameter is provided, than Paysecure will perform direct payment with the selected payment method instead of loading Paysecure URL.

### Possible Error Messages

| **Error Messages** | **Description** |
| --- | --- |
| Invalid format of Date_of_Birth\[allowed format: yyyy-mm-dd\] |  |
| Enter Valid Email |  |
| Please submit Valid Alpha2 Country Code Ex:(AF,IN) in \\"country\\" parameter |  |
| Please pass Valid State Code |  |
| Please pass valid street address in \\"street_address\\" parameter |  |
| Please pass valid city name in \\"city\\" parameter |  |
| Please pass valid postal Code name in \\"zip_code\\" parameter |  |
| You are not Allowed for Live Transaction |  |
| Minimum amount is not set for this merchant |  |
| success_redirect/failure_redirect/brand_id is missing |  |
| brand_id cannot be null |  |
| success_redirect cannot be null |  |
| failure_redirect cannot be null |  |
| Invalid failure_redirect: minimum 10 characters |  |
| purchase.products.price cannot be null |  |
| purchase.products\[0\].name/purchase.products\[0\].price are missing |  |
| Your charges setting is incomplete .Plese Contact to Administrator. |  |
| Currency "{curr_name}" is Not Allowed |  |
| Transaction amount must be equal or greater to minimum trans amount |  |
| Allowed Limit for this card for particular time period has been consumed |  |

**Note:** For certain use cases, in addition to long format purchase Id, Paysecure also provides a 7 digit unique code for each purchase starting with digit 4, eg 4000001

_“purchaseIdShortCode”: “4000013"_

:information_source: **Note** This endpoint does not require authentication.

```ts
async createPurchase1(
  body: CreatePurchaseRequest1,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreatePurchaseRequest1`](../../doc/models/create-purchase-request-1.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const body: CreatePurchaseRequest1 = {
  client: {
    email: 'ziangani@outlook.com',
    streetAddress: 'Mansarovar, Jaipur',
    city: 'Jaipur',
    fullName: 'Adarsh Saini',
    zipCode: '101100',
    country: 'IN',
    dateOfBirth: '1977-05-10',
    stateCode: 'NA',
    phone: '0964926646',
  },
  purchase: {
    currency: 'INR',
    products: [
      {
        name: 'test',
        price: 1,
      }
    ],
  },
  paymentMethod: 'THIRDPARTY-UPI',
  brandId: '{brand_id}',
  successRedirect: 'https://staging.paysecure.net/getResponse.jsp?success=true',
  pendingRedirect: 'https://staging.paysecure.net/getResponse.jsp?success=pending',
  failureRedirect: 'https://staging.paysecure.net/getResponse.jsp?success=false',
  successCallback: 'https://staging.paysecure.net',
  failureCallback: 'https://staging.paysecure.net',
};

try {
  const response = await payinApi.createPurchase1(body);

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

This API tells you about all the details of a purchase (PayIn), including its history

**Note:** With respect to bank transfers, the purchase request is synonymous with the PayIn request.

### Mandatory

you need to pass the `PurchaseID` in the API URL

### Possible Value of Status

| **Status** | **Notes** |
| --- | --- |
| paid | Transaction Successful |
| payment_in_process | Payment is under Processing |
| expired | Purchase has Expired. |
| error | Transaction has Failed. |

### Response Examples

In the response examples you can see instances of both `Paid` and `Error` Status purchases.

### Error Details

If there are any issues on the Purchase you can get more details from the `transaction_data.attempts.error` attribute of the response object

### Errors

If there are any errors then it'll be in the format of :

```json
{
    "message": "descriptive error message",
    "code": "error_code"
}

```

Please see the Status Code section for further details.

:information_source: **Note** This endpoint does not require authentication.

```ts
async getStatus1(
  purchaseId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PurchasesSuccess5>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchasesSuccess5`](../../doc/models/purchases-success-5.md).

## Example Usage

```ts
const purchaseId = 'purchaseId2';

try {
  const response = await payinApi.getStatus1(purchaseId);

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
  "purchaseId": "66c4667bb993c970367c288a",
  "client": {
    "email": "deepakdeepaksinghal@gmail.com",
    "date_of_birth": "1970-07-10",
    "street_address": "10 New Burlington Street Apt. 214",
    "country": "IN",
    "city": "London",
    "zip_code": "W1S 3BE",
    "cc": [],
    "bcc": [],
    "stateCode": "QLD"
  },
  "updated_on": 1724147324,
  "type": "purchase",
  "paymentMethod": "UPI",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "redirectType": "POST",
  "force_recurring": false,
  "created_on": 1724147324,
  "merchantRef": "66c4667bb993c970367c288a",
  "merchantName": "merchant002",
  "purchase": {
    "currency": "INR",
    "products": [
      {
        "name": "test",
        "quantity": 1,
        "price": 10,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 10,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1,
    "expireInMin": "35",
    "request_client_details": [],
    "timezone": "MIT",
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 10,
    "currency": "INR",
    "net_amount": 10,
    "fee_amount": 0,
    "pending_amount": 0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1724147324,
    "remote_paid_on": 1724147324
  },
  "issuer_details": {
    "website": "",
    "legal_street_address": "",
    "legal_country": "",
    "legal_city": "",
    "legal_zip_code": "",
    "bank_accounts": [
      {}
    ],
    "legal_name": "test6",
    "brand_name": "test6",
    "registration_number": "",
    "tax_number": ""
  },
  "transaction_data": {
    "payment_method": "",
    "flow": "payform",
    "extra": {
      "amount": 10,
      "masked_pan": "UPI"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "103.59.75.113",
        "type": "execute",
        "payment_method": "UPI",
        "flow": "payform",
        "successful": true,
        "country": "UPI",
        "processing_time": 1724147324,
        "extra": {
          "amount": 10,
          "masked_pan": "UPI"
        }
      }
    ]
  },
  "status": "PAYMENT_IN_PROCESS",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1724147324
    },
    {
      "status": "pending_execute",
      "timestamp": 1724147324
    },
    {
      "status": "payment_in_process",
      "timestamp": 1724147324
    }
  ],
  "is_test": false,
  "brand_id": "c4003b2c-22d4-4dc1-ad0c-c6b54f8c9636",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS10907",
  "issued": "2024-08-20",
  "due": 1724147324,
  "refund_upto": 1725871728,
  "cc_descriptor": "test1",
  "fraudScore": "NA",
  "trustScore": "NA",
  "payInDetails": {
    "qrCode": "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",
    "gpayUri": "gpay://upi/pay?ver=01&mode=15&am=5.00&mam=1.00&cu=INR&pa=npstpay@timecosmos&pn=NPST%20PAY&mc=6012&tr=NPST040120220010&tn=QR%20SIT%20testing&mid=NPSTPAY001&msid=NPSTPAY001-001&mtid=NPSTPAY001-001&category=02&url=http://google.com",
    "phonepeUri": "phonepe://pay?ver=01&mode=15&am=5.00&mam=1.00&cu=INR&pa=npstpay@timecosmos&pn=NPST%20PAY&mc=6012&tr=NPST040120220010&tn=QR%20SIT%20testing&mid=NPSTPAY001&msid=NPSTPAY001-001&mtid=NPSTPAY001-001&category=02&url=http://google.com",
    "paytmUri": "paytmmp://pay?ver=01&mode=15&am=5.00&mam=1.00&cu=INR&pa=npstpay@timecosmos&pn=NPST%20PAY&mc=6012&tr=NPST040120220010&tn=QR%20SIT%20testing&mid=NPSTPAY001&msid=NPSTPAY001-001&mtid=NPSTPAY001-001&category=02&url=http://google.com",
    "generatedLink": "https://staging.decf.in/pay/514o5z3m9z"
  },
  "refund_availability": "NONE",
  "refundable_amount": 10,
  "success_redirect": "https://staging.paysecure.net/getResponse.jsp?success=true",
  "failure_redirect": "https://staging.paysecure.net/getResponse.jsp?success=false",
  "cancel_redirect": "",
  "success_callback": "https://staging.paysecure.net",
  "failure_callback": "https://staging.paysecure.net",
  "platform": "API",
  "created_from_ip": "103.59.75.113",
  "checkout_url": "https://staging.paysecure.net/payments/66c4667bb993c970367c288a/",
  "payoutProcess": false
}
```

