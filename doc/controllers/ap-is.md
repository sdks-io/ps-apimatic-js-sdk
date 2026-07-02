# AP Is

```ts
const apIsApi = new ApIsApi(client);
```

## Class Name

`ApIsApi`

## Methods

* [Purchase](../../doc/controllers/ap-is.md#purchase)
* [S2 S](../../doc/controllers/ap-is.md#s2-s)
* [Payment to Be Initiated from Client Browser](../../doc/controllers/ap-is.md#payment-to-be-initiated-from-client-browser)
* [Get Status](../../doc/controllers/ap-is.md#get-status)
* [Refund](../../doc/controllers/ap-is.md#refund)
* [Payment Methods](../../doc/controllers/ap-is.md#payment-methods)
* [Cancel](../../doc/controllers/ap-is.md#cancel)
* [Check White List](../../doc/controllers/ap-is.md#check-white-list)
* [Whitelist Upload](../../doc/controllers/ap-is.md#whitelist-upload)
* [Pay Out](../../doc/controllers/ap-is.md#pay-out)
* [Purchases](../../doc/controllers/ap-is.md#purchases)
* [Session](../../doc/controllers/ap-is.md#session)
* [Get Status 5](../../doc/controllers/ap-is.md#get-status-5)
* [Purchases 1](../../doc/controllers/ap-is.md#purchases-1)
* [Session 1](../../doc/controllers/ap-is.md#session-1)
* [Get Status 1](../../doc/controllers/ap-is.md#get-status-1)
* [Purchases Encrypted Flow](../../doc/controllers/ap-is.md#purchases-encrypted-flow)
* [Purchases Decrypted Flow](../../doc/controllers/ap-is.md#purchases-decrypted-flow)
* [Get Status 2](../../doc/controllers/ap-is.md#get-status-2)
* [Purchases Encrypted Flow 1](../../doc/controllers/ap-is.md#purchases-encrypted-flow-1)
* [Purchases Decrypted Flow 1](../../doc/controllers/ap-is.md#purchases-decrypted-flow-1)
* [Get Status 3](../../doc/controllers/ap-is.md#get-status-3)
* [Purchase 1](../../doc/controllers/ap-is.md#purchase-1)
* [Get Status 11](../../doc/controllers/ap-is.md#get-status-11)
* [Refund 1](../../doc/controllers/ap-is.md#refund-1)
* [Create Customer](../../doc/controllers/ap-is.md#create-customer)
* [Get Customer](../../doc/controllers/ap-is.md#get-customer)
* [Create Session CIT](../../doc/controllers/ap-is.md#create-session-cit)
* [Create Purchase CIT](../../doc/controllers/ap-is.md#create-purchase-cit)
* [S2 S API](../../doc/controllers/ap-is.md#s2-s-api)
* [Get Mandate](../../doc/controllers/ap-is.md#get-mandate)
* [Create Purchase MIT](../../doc/controllers/ap-is.md#create-purchase-mit)
* [Revoke Mandate](../../doc/controllers/ap-is.md#revoke-mandate)
* [Pause Mandate](../../doc/controllers/ap-is.md#pause-mandate)
* [List Mandates](../../doc/controllers/ap-is.md#list-mandates)
* [Get Status 4](../../doc/controllers/ap-is.md#get-status-4)
* [List Saved Cards](../../doc/controllers/ap-is.md#list-saved-cards)
* [Purchase 2](../../doc/controllers/ap-is.md#purchase-2)
* [S2 S Payment](../../doc/controllers/ap-is.md#s2-s-payment)
* [Delete Token](../../doc/controllers/ap-is.md#delete-token)
* [Pay Out 1](../../doc/controllers/ap-is.md#pay-out-1)
* [Purchase 3](../../doc/controllers/ap-is.md#purchase-3)
* [S2 S1](../../doc/controllers/ap-is.md#s2-s1)
* [Capture](../../doc/controllers/ap-is.md#capture)
* [Cancel 1](../../doc/controllers/ap-is.md#cancel-1)


# Purchase

To Initiate a payment, the very first call to make is `/purchases` with the required data in the request body.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.email | The customer's email. |
| client.city | The customer's city. |
| client.country | ISO-3166 Country Code. Must be upper case. Example “SG” (Alpha2) |
| client.stateCode | Example “AL”, “XZ”. Must be in upper case. |
| Client.street_address | The customer's address. |
| client.zip_code | The customer's ZIP or postal code. If country=US, zip format must be NNNNN or NNNNN-NNNN. |
| purchase.currency | ISO 4217 code for currency you want to send the transaction in.  <br>  <br>Please note, the currency has to be enabled by the account manager for your account. |
| purchase.products | An object which contains the list of products which the customer is buying. |
| purchase.products.name | The name of the product. |
| purchase.products.price | Price in decimal format.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
| brand_id | Obtain from Dashboard section of your merchant account login. |
| success_redirect | URL to send the user if the transactions is successful. |
| pending_redirect | URL to send the user if the transactions is in pending. |
| failure_redirect | URL to send the user if the transactions is unsuccessful. |

## Essential Optional Parameters

### merchantRef

The `merchantRef` parameter, although not mandatory, is strongly advised for merchants to specify. Its inclusion offers two significant advantages for the merchant:

1. **Prevention of Duplicate Requests:** When a `merchantRef` is utilized, it acts as a unique identifier. This means that if a second purchase request is made using the same `merchantRef` (reference number), the system will recognize it and prevent duplicate transactions from occurring. This prevents unintended or duplicate purchases.

2. **Facilitation of Transaction Retrieval:** In situations where the response from the initial purchase request times out or the 'purchaseId' isn't received, having the `merchantRef` allows the merchant to retrieve detailed transaction information. This ensures they can track and access the specific purchase details related to that reference, even if the immediate response was not received.

However, if the merchant does not specify the 'merchantRef' parameter, the platform will automatically assign and use an internal 'purchaseId' as a reference for that transaction.

Upon successul create on a Purchase you'd get a `"purchaseId"` . Use this ID for the next step in Server to server call by calling `p/{purchaseId}/?s2s=true .`

### paymentMethod

The `paymentMethod` parameter identifies which payment solution merchant wants to use to perform a transaction. If parameter is provided, than Paysecure will perform direct payment with the selected payment method instead of loading Paysecure URL.

### Errors

If there are any errors then it'll be in the format of :

```json
{
    "message": "descriptive error message",
    "code": "error_code"
}

```

### Possible Error Messages

| **Error Messages** |
| --- |
| Allowed Limit for this card for particular time period has been consumed |
| some Mandatory Parameter are missing |
| Invalid format of Date_of_Birth \[allowed format: yyyy-mm-dd\] |
| Invalid Email Format |
| Please submit Valid Alpha2 Country Code Ex:(AF,IN) in \\"country\\" parameter |
| Please pass Valid State Code |
| Please pass valid street address in \\"street_address\\" parameter |
| Please pass valid city name in \\"city\\" parameter |
| Please pass valid postal Code name in \\"zip_code\\" parameter |
| You are not Allowed for Live Transaction |
| Merchant Limit is not set |
| Minimum amount is not set for this merchant |
| Brand not found ! |
| Your charges setting is incomplete .Plese Contact to Administrator. |
| Only {{currencyCode}} currency is allowed. |
| Transaction amount must be equal or greater to minimum trans amount |
| Invalid_Parameter  <br>You'd usually get it when one or more mandatory parameters are not present in the request. |

:information_source: **Note** This endpoint does not require authentication.

```ts
async purchase(
  body: PurchaseRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchaseRequest`](../../doc/models/purchase-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success`](../../doc/models/success.md).

## Example Usage

```ts
const body: PurchaseRequest = {
  client: {
    email: 'rahultest@gmail.com',
    streetAddress: 'Praça João da Silva Machado, 909',
    city: 'Jaipur',
    fullName: 'Rahul Agarwal',
    zipCode: '01000-000',
    country: 'IN',
    dateOfBirth: '1991-07-10',
    stateCode: 'SP',
    phone: '+91 9634458881',
  },
  purchase: {
    currency: 'EUR',
    products: [
      {
        name: 'e-commerce',
        price: '5',
      }
    ],
  },
  merchantRef: 'rahul2345test',
  paymentMethod: 'MASTER',
  brandId: 'your-brand-id',
  successRedirect: '//your.success.redirect.com',
  pendingRedirect: '//your.pending.redirect.com',
  failureRedirect: '//your.failue.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
};

try {
  const response = await apIsApi.purchase(body);

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
  "purchaseId": "6a1d26a3d373e5fd3c44ae14",
  "client": {
    "customerId": "NA",
    "email": "rahultest@gmail.com",
    "phone": "6393000899",
    "street_address": "test test",
    "country": "IN",
    "city": "123",
    "zip_code": "234567",
    "cc": [],
    "bcc": [],
    "stateCode": "ca"
  },
  "updated_on": 1780295331,
  "type": "purchase",
  "paymentMethod": "MASTER,VISA,JCB,VIRTUAL-CARD,MOBILEMONEY,UPI-INTENT,UPI-QR,INTERAC-E-TRANSFER,INTERAC-REQUEST-MONEY,INTERAC-EXPRESS,PIX,FawryPay,OPEN-BANKING,SPEI",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "errorCode": "NA",
  "force_recurring": false,
  "created_on": 1780295331,
  "merchantRef": "rahul2345@gmail.co",
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "name": "product name",
        "quantity": 1.0,
        "price": 10.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 10.0,
    "requestAmount": 10.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "taxAmount": 0.0,
    "taxPercent": 0.0,
    "request_client_details": [],
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
    "legal_name": "Final_cashier",
    "brand_name": "Final_cashier",
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
      "timestamp": 1780295331
    }
  ],
  "is_test": false,
  "brand_id": "76067f4a-3155-4bf0-872b-a77a382d4cf7",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS1172",
  "issued": "2026-06-01",
  "due": 1780295331,
  "refund_upto": 0,
  "cc_descriptor": "",
  "fraudScore": "NA",
  "trustScore": "NA",
  "extraFee": "0",
  "totalRefunded": 0.0,
  "paidOn": 0,
  "receivedAmt": 0.0,
  "taxAmount": 0.0,
  "surcharge": 0.0,
  "surchargeType": "",
  "sessionId": "",
  "refund_availability": "NONE",
  "refundable_amount": 0.0,
  "success_redirect": "https://your.success.redirect.com",
  "failure_redirect": "https://your.failure.redirect.com",
  "pending_redirect": "https://your.pending.redirect.com",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.com",
  "failure_callback": "https://your.failure.callback.com",
  "platform": "API",
  "created_from_ip": "103.80.161.238",
  "checkout_url": "https://test4.paymentsclub.net/payments/c3f2eee71c5824b75c7b52ff41e76814/",
  "direct_post_url": "https://test4.paymentsclub.net/api/v1/p/6a1d26a3d373e5fd3c44ae14/",
  "payoutProcess": false
}
```


# S2 S

This API would be the 2nd in sequence to call if the call to `/purchases/` was successful in step 1. and you want to do the transaction via Server-to-Server mode.

The request body would contain the details of the card that's to be transacted upon.

### **Mandatory parameters in request body:**

| Parameter | **Notes** |
| --- | --- |
| remote_ip | IP address of the customer’s device used for transaction. Helps in fraud checks and risk scoring. Ex- 157.38.242.7 |
| remember_card | "on" or "off" if you want us to store the card details on our end. |
| user_agent | Full browser and operating system details captured from HTTP header. EX- Chrome/5.0 (X11; Linux x86_64) |
| accept_header | Browser’s accepted content types (from HTTP header). Used for validating request origin and device info. EX- text/html |

**Note:**  
If you want to use token_reference for doing a card transaction, please have a look at Network Tokenisation Section.

### **Essential parameters in request body:**

| Parameter | **Notes** |
| --- | --- |
| cardholder_name | Name of the cardholder |
| card_number | The card numbers Must be 10-20 characters. |
| expires | must be greater than the current month/year. MM/YY format. |
| cvc | 3 or 4 digit |

**Other optional parameters in request body:**

| Parameter | **Notes** |
| --- | --- |
| language | Preferred language of the user’s browser . EX - en-US |
| java_enabled | Indicates if Java is enabled in the browser. Helps PSPs in device profiling. Ex- true/false |
| javascript_enabled | Indicates if JavaScript is enabled in the client browser. Used for 3DS or risk-based checks. Ex- true |
| color_depth | Bit depth of the display screen. Ex- 24 |
| utc_offset | Difference in minutes between local time and UTC. Used for location and timezone checks. Ex- 330 |
| screen_width | Width of the device screen in pixels. Used in device profiling. Ex- 1920 |
| screen_height | Height of the device screen in pixels. Ex- 1080 |

### Successful Response

If all the details are correct you'll get a 202 response with staus as Pending

```json
{
    "status": "pending",
    "callback_url": "https://paysecure.net/payment/63bd0bf80fb42a076e8a4dd1/",
    "method": "GET"
}

```

If the response code is 202, after receiving the response body, direct the customer to the callback_url provided in the response.

### Errors

If there are any errors then it'll be in the format of :

```json
{
    "message": "descriptive error message",
    "code": "error_code"
}

```

Please see the Status Code section for further details.

| **Error Messages** |
| --- |
| Client Ip could not be matched with Merchant Ip |
| Invalid Card Information |
| Card is Blocked |
| Different Type of key used to create purchase and payment |
| You charges setting is incomplete .Plese Contact to adminstrartor. |
| Allowed Attempt for this Transaction has been consumed |
| Invalid Card Expiry(Valid Format:MM/YY) must be greator than current month/year |
| Customer profile is Blocked |
| Customer/Card not allowed for transaction |

:information_source: **Note** This endpoint does not require authentication.

```ts
async s2S(
  s2S: boolean,
  body: S2Srequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success1>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `s2S` | `boolean` | Query, Required | - |
| `body` | [`S2Srequest`](../../doc/models/s2-srequest.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success1`](../../doc/models/success-1.md).

## Example Usage

```ts
const s2S = true;

const body: S2Srequest = {
  cardholderName: 'dk',
  cardNumber: '4111111111111111',
  expires: '10/23',
  cvc: '345',
  rememberCard: 'on',
  remoteIp: '157.38.242.7',
  userAgent: 'Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/51.0.2704.103 Safari/537.36',
  acceptHeader: 'text/html',
  language: 'en-US',
  javaEnabled: false,
  javascriptEnabled: true,
  colorDepth: 24,
  utcOffset: 0,
  screenWidth: 1920,
  screenHeight: 1080,
};

try {
  const response = await apIsApi.s2S(
    s2S,
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
    if (error instanceof FailureError) {
      console.log(error.result);
    }
  }
}
```

## Example Response *(as JSON)*

```json
{
  "status": "pending",
  "callback_url": "http://18.214.100.20/api/v1/payment/64b034ecc6dccf7d329d9eb3/",
  "method": "GET"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | [`FailureError`](../../doc/models/failure-error.md) |


# Payment to Be Initiated from Client Browser

This is the callback URL that is in the response object of the Server-to-Server Call

When this URL is called from the end user's browser, the user would be redirected to the `success_redirect` or `failure_redirect` URL given by the merchant at the time of create purchase

When this URL is called from the end user's browser, if card is 3DS enrolled, the user will be redirect to a verification screen or challenge by the issuing bank and upon successful user verification, the user would be redictected to the success URL given in `/purchases API` .

If for some reason the transactions is unsuccessful, the user will be redirect to failure URL given in `/purchases API` API .

:information_source: **Note** This endpoint does not require authentication.

```ts
async paymentToBeInitiatedFromClientBrowser(
  accept: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accept` | `string` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const accept = 'application/json';

try {
  const response = await apIsApi.paymentToBeInitiatedFromClientBrowser(accept);

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
    if (error instanceof PaymentError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`PaymentError`](../../doc/models/payment-error.md) |


# Get Status

This API tells you about all the details of a purchase, including its history

### Mandatory

you need to pass the `PurchaseID` in the API URL

### Possible Value of Status

| **Status** | **Notes** |
| --- | --- |
| created | When Purchase order is created. |
| paid | Transaction Successful |
| payment_in_process | Payment is under Processing |
| chargeback | Payment is chargeback state |
| refund_in_process | Refund is under Processing. |
| expired | Purchase has Expired. |
| overdue | Purchase is Overdued. |
| cancelled | Purchase is cancelled. |
| error | Transaction has Failed. |
| refunded | Payment is refunded |

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
  requestOptions?: RequestOptions
): Promise<ApiResponse<PurchasesError>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchasesError`](../../doc/models/purchases-error.md).

## Example Usage

```ts
try {
  const response = await apIsApi.getStatus();

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
  "purchaseId": "64bfd7c9f63e36669499e779",
  "client": {
    "bank_account": "",
    "bank_code": "",
    "email": "example@paysecure.net",
    "phone": "",
    "full_name": "",
    "date_of_birth": "",
    "personal_code": "",
    "street_address": "test test",
    "country": "IN",
    "city": "123",
    "zip_code": "234567",
    "shipping_street_address": "",
    "shipping_country": "",
    "shipping_city": "",
    "shipping_zip_code": "",
    "cc": [],
    "bcc": [],
    "legal_name": "",
    "brand_name": "",
    "registration_number": "",
    "tax_number": "",
    "stateCode": "ca"
  },
  "updated_on": 1690294251,
  "type": "purchase",
  "force_recurring": false,
  "created_on": 1690294220,
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "name": "dk",
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
    "request_client_details": [],
    "timezone": "America/Edmonton",
    "email_message": ""
  },
  "issuer_details": {
    "website": "",
    "legal_street_address": "",
    "legal_country": "",
    "legal_city": "",
    "legal_zip_code": "",
    "bank_accounts": [
      {
        "bank_account": "",
        "bank_code": ""
      }
    ],
    "legal_name": "shoes",
    "brand_name": "shoes",
    "registration_number": "",
    "tax_number": ""
  },
  "transaction_data": {
    "payment_method": "",
    "flow": "payform",
    "extra": {
      "expiry_month": "10",
      "amount": 100,
      "card_issuer": "1-800-432-3117",
      "masked_pan": "411111XXXXXX1111",
      "card_brand": "VISA",
      "card_issuer_country": "US",
      "cardholder_name": "dk",
      "expiry_year": "23"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "149.86.53.48",
        "type": "execute",
        "payment_method": "VISA",
        "flow": "payform",
        "successful": false,
        "country": "US",
        "processing_time": 1690294279,
        "extra": {
          "expiry_month": "10",
          "amount": 100,
          "card_issuer": "1-800-432-3117",
          "masked_pan": "411111XXXXXX1111",
          "card_brand": "VISA",
          "card_issuer_country": "US",
          "cardholder_name": "dk",
          "expiry_year": "23"
        },
        "error": {
          "message": "Transaction Failed",
          "code": "transaction_error"
        }
      }
    ]
  },
  "status": "ERROR",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1690294220
    },
    {
      "status": "pending_execute",
      "timestamp": 1690294251
    },
    {
      "status": "error",
      "timestamp": 1690294299
    },
    {
      "status": "viewed",
      "timestamp": 1690294382
    }
  ],
  "viewedOn": 1690299845,
  "is_test": false,
  "brand_id": "bd69e8a5-adcf-40de-9e43-2b87cb129a5e",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS188",
  "issued": "2023-07-25",
  "due": 1690294220,
  "refund_upto": 0,
  "cc_descriptor": "",
  "refund_availability": "NONE",
  "refundable_amount": 0,
  "success_redirect": "https://google.com",
  "failure_redirect": "https://yahoo.com",
  "cancel_redirect": "",
  "success_callback": "",
  "platform": "API",
  "created_from_ip": "149.86.53.48",
  "checkout_url": "http://18.214.100.20/payments/64bfd7c9f63e36669499e779/",
  "direct_post_url": "http://18.214.100.20/api/v1/p/64bfd7c9f63e36669499e779/"
}
```


# Refund

This API is used to initate refund (Full Refund) of the purchases that have status as `PAID` can be initiated for refund

Once the refund has been initiated, the status of the purchase would become `REFUND_IN_PROCESS` and once the refund has been approved by the bank, the status woud become `REFUNDED`

Purchase ID is **mandatory** for this API.

Currently we don't support partial refunds.

### Response Examples

In the response examples you can see instances of both `successful` and `unsuccessful` in refund of purchases.

:information_source: **Note** This endpoint does not require authentication.

```ts
async refund(
  requestOptions?: RequestOptions
): Promise<ApiResponse<RefundSuccess>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`RefundSuccess`](../../doc/models/refund-success.md).

## Example Usage

```ts
try {
  const response = await apIsApi.refund();

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
    if (error instanceof RefundError) {
      console.log(error.result);
    }
  }
}
```

## Example Response *(as JSON)*

```json
{
  "purchaseId": "64bfdb7df63e36669499e82f",
  "client": {
    "customerId": "NA",
    "email": "divya@paysecure.net",
    "phone": "6393000899",
    "full_name": "Test",
    "date_of_birth": "07/01/2000",
    "street_address": "test test",
    "country": "IN",
    "city": "123",
    "zip_code": "234567",
    "cc": [],
    "bcc": [],
    "stateCode": "ca"
  },
  "updated_on": 1690302819,
  "type": "purchase",
  "force_recurring": false,
  "created_on": 1690295168,
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "name": "dk",
        "quantity": 1,
        "price": 9,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 9,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1,
    "request_client_details": [],
    "timezone": "America/Edmonton",
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 9,
    "currency": "USD",
    "net_amount": 9,
    "fee_amount": 10.2591,
    "pending_amount": 0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1690295205,
    "remote_paid_on": 1690295205
  },
  "issuer_details": {
    "website": "",
    "legal_street_address": "",
    "legal_country": "",
    "legal_city": "",
    "legal_zip_code": "",
    "bank_accounts": [
      {
        "bank_account": "",
        "bank_code": ""
      }
    ],
    "legal_name": "shoes",
    "brand_name": "shoes",
    "registration_number": "",
    "tax_number": ""
  },
  "transaction_data": {
    "payment_method": "",
    "flow": "payform",
    "extra": {
      "expiry_month": "10",
      "amount": 9,
      "card_issuer": "1-800-432-3117",
      "masked_pan": "411111XXXXXX1111",
      "card_brand": "VISA",
      "card_issuer_country": "US",
      "cardholder_name": "dk",
      "expiry_year": "23"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "149.86.53.48",
        "type": "execute",
        "payment_method": "VISA",
        "flow": "payform",
        "successful": true,
        "country": "US",
        "processing_time": 1690295205,
        "extra": {
          "expiry_month": "10",
          "amount": 9,
          "card_issuer": "1-800-432-3117",
          "masked_pan": "411111XXXXXX1111",
          "card_brand": "VISA",
          "card_issuer_country": "US",
          "cardholder_name": "dk",
          "expiry_year": "23"
        }
      },
      {
        "client_ip": "149.86.53.48",
        "type": "refund",
        "successful": true,
        "processing_time": 1690302819,
        "extra": {
          "amount": 9
        }
      }
    ]
  },
  "status": "REFUNDED",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1765294731
    },
    {
      "status": "pending_execute",
      "timestamp": 1765294744
    },
    {
      "status": "payment_in_process",
      "timestamp": 1765294754
    },
    {
      "status": "paid",
      "timestamp": 1765297331
    },
    {
      "status": "refunded",
      "timestamp": 1765624009
    }
  ],
  "viewedOn": 1690299929,
  "is_test": false,
  "brand_id": "bd69e8a5-adcf-40de-9e43-2b87cb129a5e",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS192",
  "issued": "2023-07-25",
  "due": 1690295168,
  "refund_upto": 1705843623,
  "cc_descriptor": "test-cardeye",
  "refund_availability": "NONE",
  "refundable_amount": 0,
  "success_redirect": "https://google.com",
  "failure_redirect": "https://yahoo.com",
  "cancel_redirect": "",
  "success_callback": "",
  "platform": "API",
  "created_from_ip": "149.86.53.48",
  "checkout_url": "http://18.214.100.20/payments/64bfdb7df63e36669499e82f/",
  "direct_post_url": "http://18.214.100.20/api/v1/p/64bfdb7df63e36669499e82f/"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`RefundError`](../../doc/models/refund-error.md) |


# Payment Methods

This API gives back the list of Payment methods available for a brand.

:information_source: **Note** This endpoint does not require authentication.

```ts
async paymentMethods(
  brandId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PaymentMethodSuccess>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `brandId` | `string` | Query, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PaymentMethodSuccess`](../../doc/models/payment-method-success.md).

## Example Usage

```ts
const brandId = 'your-brand-id';

try {
  const response = await apIsApi.paymentMethods(brandId);

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
    if (error instanceof PaymentMethodsError) {
      console.log(error.result);
    }
  }
}
```

## Example Response *(as JSON)*

```json
{
  "available_payment_methods": [
    "MASTER",
    "visa",
    "jcb",
    "amex",
    "CRYPTO-BRIDGE",
    "FawryPay",
    "INTERAC-E-TRANSFER",
    "INTERAC-REQUEST-MONEY",
    "MOBILEMONEY",
    "NEOSURF",
    "PAYID",
    "PIX",
    "SPEI",
    "THIRDPARTY-UPI",
    "discover",
    "BANKTRANSFER",
    "VIRTUAL-IBAN",
    "UPI-COLLECT",
    "UPI-QR",
    "VIRTUAL-ACCOUNT",
    "DINERS",
    "NETBANKING"
  ],
  "by_country": {
    "any": [
      "MASTER",
      "VISA",
      "JCB",
      "AMEX",
      "CRYPTO-BRIDGE",
      "FawryPay",
      "INTERAC-E-TRANSFER",
      "INTERAC-REQUEST-MONEY",
      "MOBILEMONEY",
      "NEOSURF",
      "PAYID",
      "PIX",
      "SPEI",
      "THIRDPARTY-UPI",
      "DISCOVER",
      "BANKTRANSFER",
      "VIRTUAL-IBAN",
      "UPI-COLLECT",
      "UPI-QR",
      "VIRTUAL-ACCOUNT",
      "DINERS",
      "NETBANKING"
    ]
  },
  "country_names": {
    "any": "Other"
  },
  "names": {
    "NETBANKING": "NETBANKING",
    "AMEX": "AMEX",
    "MASTER": "Mastercard",
    "CRYPTO-BRIDGE": "CRYPTO-BRIDGE",
    "PAYID": "PAYID",
    "SPEI": "SPEI",
    "DISCOVER": "DISCOVER",
    "JCB": "JCB",
    "VISA": "Visa",
    "NEOSURF": "NEOSURF",
    "INTERAC-E-TRANSFER": "INTERAC-E-TRANSFER",
    "THIRDPARTY-UPI": "THIRDPARTY-UPI",
    "VIRTUAL-IBAN": "VIRTUAL-IBAN",
    "BANKTRANSFER": "BANKTRANSFER",
    "DINERS": "DINERS",
    "INTERAC-REQUEST-MONEY": "INTERAC-REQUEST-MONEY",
    "UPI-COLLECT": "UPI-COLLECT",
    "UPI-QR": "UPI-QR",
    "MOBILEMONEY": "MOBILEMONEY",
    "FawryPay": "FawryPay",
    "VIRTUAL-ACCOUNT": "VIRTUAL-ACCOUNT",
    "PIX": "PIX"
  },
  "card_methods": [
    "MASTER",
    "VISA",
    "JCB",
    "AMEX",
    "DISCOVER"
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | [`PaymentMethodsError`](../../doc/models/payment-methods-error.md) |


# Cancel

Cancels an in-progress or completed purchase transaction, preventing further processing or reversing the authorization hold. Use this endpoint to void a transaction that has not yet been settled to the merchant's account.

**When to use:**

- **Post-creation cancellation:** Cancel a purchase immediately after it has been created via the Purchase API, before the customer completes the payment flow.

- **Pre-redirect cancellation:** Cancel a transaction after completing the server-to-server (S2S) call but before redirecting the cardholder to the `callbackURL`. This is useful when your backend validation logic determines the transaction should not proceed (e.g., inventory check failure, fraud flag, duplicate order detection).

Purchase ID is **mandatory** for this API.

:information_source: **Note** This endpoint does not require authentication.

```ts
async cancel(
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success2>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success2`](../../doc/models/success-2.md).

## Example Usage

```ts
try {
  const response = await apIsApi.cancel();

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
    if (error instanceof Error1Error) {
      console.log(error.result);
    }
  }
}
```

## Example Response *(as JSON)*

```json
{
  "purchaseId": "64bff4fff63e36669499e9c8",
  "client": {
    "email": "example@paysecure.net",
    "phone": "",
    "full_name": "",
    "date_of_birth": "",
    "personal_code": "",
    "street_address": "test test",
    "country": "IN",
    "city": "123",
    "zip_code": "234567",
    "shipping_street_address": "",
    "shipping_country": "",
    "shipping_city": "",
    "shipping_zip_code": "",
    "cc": [],
    "bcc": [],
    "legal_name": "",
    "brand_name": "",
    "registration_number": "",
    "tax_number": "",
    "stateCode": "ca"
  },
  "updated_on": 1690301735,
  "type": "purchase",
  "force_recurring": false,
  "created_on": 1690301698,
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "name": "dk",
        "quantity": 1,
        "price": 9,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 9,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1,
    "request_client_details": [],
    "timezone": "America/Edmonton",
    "email_message": ""
  },
  "issuer_details": {
    "website": "",
    "legal_street_address": "",
    "legal_country": "",
    "legal_city": "",
    "legal_zip_code": "",
    "bank_accounts": [
      {
        "bank_account": "",
        "bank_code": ""
      }
    ],
    "legal_name": "shoes",
    "brand_name": "shoes",
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
  "status": "CANCELLED",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1690301698
    },
    {
      "status": "pending_execute",
      "timestamp": 1690301723
    },
    {
      "status": "cancelled",
      "timestamp": 1690301735
    }
  ],
  "is_test": false,
  "brand_id": "bd69e8a5-adcf-40de-9e43-2b87cb129a5e",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS194",
  "issued": "2023-07-25",
  "due": 1690301698,
  "refund_upto": 0,
  "cc_descriptor": "",
  "refund_availability": "NONE",
  "refundable_amount": 0,
  "success_redirect": "https://google.com",
  "failure_redirect": "https://yahoo.com",
  "cancel_redirect": "",
  "success_callback": "",
  "platform": "API",
  "created_from_ip": "149.86.53.48",
  "checkout_url": "http://18.214.100.20/payments/64bff4fff63e36669499e9c8/",
  "direct_post_url": "http://18.214.100.20/api/v1/p/64bff4fff63e36669499e9c8/"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`Error1Error`](../../doc/models/error-1-error.md) |


# Check White List

### Overview

Paysecure supports the concept of whitelisted cards. The merchant can send PaySecure a list of cards that are to be whitelisted. Once whitelisted, only whitelisted cards are allowed to be transacted for that merchant.

The merchant can check the individual card status with this API by giving the email and card numbers of the customers.

### Mandatory Parameters (in body)

| **Parameters** |
| --- |
| email |
| card_num |

### Other parameters:

| **Parameters** |
| --- |
| signup_date |
| deposit_date |
| number_of_deposits |

### Response Examples

In the response examples, you can observe both instances of verifying whether a card exists in a merchant's whitelist, one for an existing card and another for a non-existing card.

:information_source: **Note** This endpoint does not require authentication.

```ts
async checkWhiteList(
  accept: string,
  body: CheckWhiteListRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<CheckWhiteListDoesnTExists>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accept` | `string` | Header, Required | - |
| `body` | [`CheckWhiteListRequest`](../../doc/models/check-white-list-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`CheckWhiteListDoesnTExists`](../../doc/models/check-white-list-doesn-t-exists.md).

## Example Usage

```ts
const accept = 'application/json';

const body: CheckWhiteListRequest = {
  email: 'dev@paysecure.net',
  cardNum: '5178006985381351',
};

try {
  const response = await apIsApi.checkWhiteList(
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

## Example Response *(as JSON)*

```json
{
  "message": "NOTEXIST"
}
```


# Whitelist Upload

### Overview

The merchant can upload a list of whitelist cards and email ids through this API. All cards successfully uploaded will be considered whitelisted and allowed for that merchant.

### Mandatory parameters in the request body:

| Parameter | Notes |
| --- | --- |
| csvFile | Upload a CSV file |

**Please note:**

1. CSV file should contain the following headers (both mandatory)
   
   1. card_number
   
   2. email_id

2. CSV file should not be empty

```java
public class FileUploader {
    public static void uploadFile(String apiUrl, String filePath, String authorizationHeader) {
        try {
            File file = new File(filePath);
            OkHttpClient client = new OkHttpClient();
            RequestBody requestBody = new MultipartBody.Builder().setType(MultipartBody.FORM)
                    .addFormDataPart("csvFile", file.getName(), RequestBody.create(MediaType.parse("text/csv"), file))
                    .build();
            Request request = new Request.Builder().url(apiUrl).post(requestBody)
                    .addHeader("Authorization", authorizationHeader).build();
            Response response = client.newCall(request).execute();
            if (response.code() == 202) {
                System.out.println("File uploaded successfully!");
                System.out.println("Response: " + response.body().string());
            } else {
                System.out.println("File upload failed.");
                System.out.println("Status: " + response.code());
                System.out.println("Error: " + response.body().string());
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
    public static void main(String[] args) {
        String apiUrl = "https://{{base_url}}/api/v1/whitelist/upload";
        String filePath = "whitelist.csv.file.path";
        String authorizationHeader = "Bearer YOUR API KEY";
        uploadFile(apiUrl, filePath, authorizationHeader);
    }
}

```

:information_source: **Note** This endpoint does not require authentication.

```ts
async whitelistUpload(
  csvFile: FileWrapper,
  requestOptions?: RequestOptions
): Promise<ApiResponse<WhitelistUploadSuccess>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `csvFile` | `FileWrapper` | Form, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`WhitelistUploadSuccess`](../../doc/models/whitelist-upload-success.md).

## Example Usage

```ts
const csvFile = new FileWrapper(fs.createReadStream('dummy_file'));

try {
  const response = await apIsApi.whitelistUpload(csvFile);

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
    if (error instanceof WhitelistUploadFailureError) {
      console.log(error.result);
    }
  }
}
```

## Example Response *(as JSON)*

```json
{
  "totalRecords": 3,
  "totalApproved": 3,
  "status": "success"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | [`WhitelistUploadFailureError`](../../doc/models/whitelist-upload-failure-error.md) |


# Pay Out

## Overview

The **Original Credit Transaction (OCT)**, commonly referred to as **Push to Card**, enables merchants to facilitate near-instantaneous fund transfers directly to a customer’s eligible Visa or Mastercard debit or credit card. Unlike traditional refund processes that can only return funds from a previous purchase, OCT allows for independent disbursements of funds to a cardholder's account.

This feature is designed for high-velocity industries that require frictionless, real-time payouts, such as:

- **Gaming & Betting:** Real-time withdrawal of player winnings.

- **Marketplaces:** Payouts to sellers or service providers.

- **Corporate Disbursements:** Instant insurance claims, rebates, or compensation payments.

- **Merchant Settlements:** Faster access to processed funds for sub-merchants.

By utilizing the Paysecure `/payout` API with the `PAYOUT-CARDS` method, you benefit from a unified orchestration layer that handles the complexities of card network routing, ensuring high success rates and global reach while maintaining the same security standards as your standard payment integrations.

---


## Integration Steps

1. **Enable OCT:** Ensure "Push to Card" permissions are enabled for your merchant account in the Paysecure Merchant Portal.

2. **Collect Card Details:** Collect the recipient's card details securely, or use Paysecure's Cashier to collect the card information on your behalf.

3. **Execute Payout:** Call the `/payout` endpoint with the OCT-specific payout method.

4. **Handle Webhooks:** Listen for the `paid` or `failure` events to update your internal records.

### **Mandatory parameters in the request body:**

| **Parameter** | **Required** | **Notes** |
| --- | --- | --- |
| client.email | Yes | The customer's email. |
| client.phone | Yes | The customer's phone number along with the country code.  <br>Example: +91 9634088651 |
| client.city | Yes | The customer's city. |
| client.country | Yes | ISO-3166 Country Code. Must be upper case. Example “SG” (Alpha2) |
| client.stateCode | Optional | Example “AL”, “XZ”. Must be in upper case. |
| Client.street_address | Optional | The customer's address. |
| client.zip_code | Optional | The customer's ZIP or postal code. If country=US, zip format must be NNNNN or NNNNN-NNNN. |
| currency | Yes | ISO 4217 code for currency you want to send the transaction in.  <br>  <br>Please note, the currency has to be enabled by the account manager for your account. |
| amount | Yes | amount in decimal format.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
| payoutMethod | Optional | example: PAYOUT-CARDS |
| success_redirect | Yes | URL to send the user if the transactions is successful. |
| pending_redirect | Yes | URL to send the user if the transactions is in pending. |
| failure_redirect | Yes | URL to send the user if the transactions is unsuccessful. |
| Purpose | Optional | The purpose of doing a payout. |
| extraParam.cardNumber | Yes | The recipient's 16-digit card number. |
| extraParam.expiryYear | Yes | YYYY format (e.g., 2028). |
| extraParam.expiryMonth | Yes | MM format (e.g., 05). |
| extraParam.cardHolderName | Yes | The receiver's Full Name. Preferred a 2 word name with each word atleast 3 characters long. |

**Note:**

If the merchant is not PCI DSS compliant then they will need to use our **cashier** and asking the user to enter the card details there. Check the cashier section for more details. If the merchant is PCI DSS compliant then they can use the payout API and send the card details as shown above.

If the merchant wants to use **token_reference** for doing a payout, then please have a look at the Network Tokenisation Section.

:information_source: **Note** This endpoint does not require authentication.

```ts
async payOut(
  accept: string,
  body: PayOutRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accept` | `string` | Header, Required | - |
| `body` | [`PayOutRequest`](../../doc/models/pay-out-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const accept = 'application/json';

const body: PayOutRequest = {
  client: {
    email: 'rahul@gmail.com',
    country: 'GB',
    city: 'London',
    stateCode: 'QLD',
    fullName: 'Rahul Jain',
    streetAddress: '10 New Burlington Street Apt. 214',
    zipCode: 'W1S 3BE',
    phone: '+44 9876543210',
    gender: 'M',
    dateOfBirth: '1970-07-10',
  },
  purpose: 'Testing cards payout',
  currency: 'GBP',
  merchantRef: 'YOUR ORDER ID',
  payoutMethod: 'PAYOUT-CARDS',
  amount: 100,
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  extraParam: {
    cardNumber: '5431240006334004',
    cardHolderName: 'Rahul Agarwal',
    expiryYear: '2030',
    expiryMonth: '11',
  },
};

try {
  const response = await apIsApi.payOut(
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
"{\r\n    \"payoutId\": \"6977137755e0628e3600c562\",\r\n    \"client\": {\r\n        \"email\": \"rahul@gmail.com\",\r\n        \"country\": \"GB\",\r\n        \"city\": \"London\",\r\n        \"stateCode\": \"QLD\",\r\n        \"full_name\": \"Rahul Jain\",\r\n        \"street_address\": \"10 New Burlington Street Apt. 214\",\r\n        \"zip_code\": \"W1S 3BE\",\r\n        \"phone\": \"+44 9876543210\",\r\n        \"gender\": \"M\",\r\n        \"date_of_birth\": \"1970-07-10\"\r\n    },\r\n    \"updated_on\": 1769411447,\r\n    \"extraParam\": {\r\n        \"cardNumber\": \"5431240006334004\",\r\n        \"cardHolderName\": \"Rahul Agarwal\",\r\n        \"expiryYear\": \"2030\",\r\n        \"expiryMonth\": \"11\"\r\n    },\r\n    \"payoutMethod\": \"PAYOUT-CARDS\",\r\n    \"amountUnit\": \"MAJOR\",\r\n    \"amount\": 100.0,\r\n    \"errorMsg\": \"\",\r\n    \"purpose\": \"Testing cards payout\",\r\n    \"created_on\": 1769411447,\r\n    \"merchantRef\": \"YOUR ORDER ID\",\r\n    \"status\": \"PAID\",\r\n    \"status_history\": [\r\n        {\r\n            \"status\": \"created\",\r\n            \"timestamp\": 1769411447\r\n        },\r\n        {\r\n            \"status\": \"payout_in_process\",\r\n            \"timestamp\": 1769411447\r\n        },\r\n        {\r\n            \"status\": \"paid\",\r\n            \"timestamp\": 1769411447\r\n        },\r\n\r\n    ],\r\n    \"currency\": \"GBP\",\r\n    \"extraFee\": \"0\",\r\n    \"paymentOn\": 0,\r\n    \"checkout_url\": \"https://test4.paymentsclub.net/payout/092e59f94279a3742fa3715fe9a2112a/\",\r\n    \"taxAmount\": 0.0,\r\n    \"taxPercent\": 0.0,\r\n    \"success_redirect\": \"https://your.success.redirect.com\",\r\n    \"pending_redirect\": \"https://your.pending.redirect.com\",\r\n    \"failure_redirect\": \"https://your.failure.redirect.com\",\r\n    \"success_callback\": \"https://your.success.callback.com\",\r\n    \"failure_callback\": \"https://your.failure.callback.com\"\r\n    \"redirectType\": \"POST\",\r\n    \"sessionId\": \"\",\r\n    \"surcharge\": 0.0,\r\n    \"surchargeType\": \"\",\r\n    \"trxMethod\": \"CARDS\",\r\n    \"success_callback\": \"\",\r\n    \"failure_callback\": \"\"\r\n}"
```


# Purchases

To Initiate a payment, the very first call to make is `/purchases` with the required data in the request body.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.full_name | Conditional.  <br>But Recommended to pass the complete name of the client. Atleast 2 words recommended. |
| client.email | Conditional.  <br>But Recommended to pass a correct email id. |
| paymentMethod | Conditional.  <br>Mandatory if you are not using Paysecure Cashier. Else Non Mandatory.  <br>Value: GOOGLEPAY-REDIRECT |
| purchase.currency | Mandatory.  <br>ISO 4217 code for currency you want to send the transaction in. This should be 'BRL' for PIX. |
| purchase.products.name | Mandatory. |
| purchase.products.price | Mandatory.  <br>Price in decimal format upto 2 decimals.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
| brand_id | Mandatory.  <br>Obtain from Dashboard section of your merchant account login. |
| success_redirect | Mandatory.  <br>URL to send the user if the transactions is successful. |
| pending_redirect | Mandatory.  <br>URL to send the user if the transactions is in progress state. |
| failure_redirect | Mandatory  <br>URL to send the user if the transactions has failed. |

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

:information_source: **Note** This endpoint does not require authentication.

```ts
async purchases(
  body: PurchasesRequest6,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchasesRequest6`](../../doc/models/purchases-request-6.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const body: PurchasesRequest6 = {
  client: {
    email: 'rahultest@gmail.com',
    streetAddress: '10 New Burlington StreetApt. 214',
    city: 'London',
    fullName: 'Rahul Agarwal',
    zipCode: 'W1S 3BE',
    country: 'GB',
    dateOfBirth: '1994-31-04',
    stateCode: 'RJ',
    phone: '+91 9634088561',
  },
  purchase: {
    currency: 'EUR',
    products: [
      {
        name: 'gaming cards ',
        price: 10,
      }
    ],
  },
  brandId: 'your-brandid',
  paymentMethod: 'GOOGLEPAY-REDIRECT',
  successRedirect: 'https://your-redirect-url?issucces=true',
  pendingRedirect: 'https://your-redirect-url?ispending=true',
  failureRedirect: 'https://your-redirect-url?isfailure=true',
  successCallback: 'https://your-webhook-url',
  failureCallback: 'https://your-webhook-url',
};

try {
  const response = await apIsApi.purchases(body);

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
"{\r\n    \"purchaseId\": \"69634df44549cbd3547ac750\",\r\n    \"client\": {\r\n        \"customerId\": \"NA\",\r\n        \"email\": \"rahultest@gmail.com\",\r\n        \"phone\": \"+91 9634088561\",\r\n        \"full_name\": \"Rahul Agarwal\",\r\n        \"date_of_birth\": \"1994-31-04\",\r\n        \"street_address\": \"10 New Burlington StreetApt. 214\",\r\n        \"country\": \"GB\",\r\n        \"city\": \"London\",\r\n        \"zip_code\": \"W1S 3BE\",\r\n        \"cc\": [],\r\n        \"bcc\": [],\r\n        \"stateCode\": \"RJ\"\r\n    },\r\n    \"updated_on\": 1768115701,\r\n    \"type\": \"purchase\",\r\n    \"paymentMethod\": \"GOOGLEPAY-REDIRECT\",\r\n    \"amountUnit\": \"MAJOR\",\r\n    \"errorMsg\": \"\",\r\n    \"errorCode\": \"NA\",\r\n    \"force_recurring\": false,\r\n    \"created_on\": 1768115700,\r\n    \"merchantRef\": \"69634df44549cbd3547ac750\",\r\n    \"purchase\": {\r\n        \"currency\": \"EUR\",\r\n        \"products\": [\r\n            {\r\n                \"name\": \"gaming cards\",\r\n                \"quantity\": 1.0,\r\n                \"price\": 1.0,\r\n                \"discount\": 0,\r\n                \"tax_percent\": \"0.00\"\r\n            }\r\n        ],\r\n        \"total\": 1.0,\r\n        \"requestAmount\": 1.0,\r\n        \"language\": \"en\",\r\n        \"notes\": \"\",\r\n        \"debt\": 0,\r\n        \"total_formatted\": 1.0,\r\n        \"taxAmount\": 0.0,\r\n        \"taxPercent\": 0.0,\r\n        \"request_client_details\": [],\r\n        \"email_message\": \"\"\r\n    },\r\n    \"payment\": {\r\n        \"is_outgoing\": false,\r\n        \"payment_type\": \"PURCHASE\",\r\n        \"amount\": 1.0,\r\n        \"currency\": \"EUR\",\r\n        \"net_amount\": 1.0,\r\n        \"fee_amount\": 0.0,\r\n        \"pending_amount\": 0.0,\r\n        \"pending_unfreeze_on\": null,\r\n        \"description\": \"\",\r\n        \"paid_on\": 1768115700,\r\n        \"remote_paid_on\": 1768115700\r\n    },\r\n    \"issuer_details\": {\r\n        \"website\": \"\",\r\n        \"legal_street_address\": \"\",\r\n        \"legal_country\": \"\",\r\n        \"legal_city\": \"\",\r\n        \"legal_zip_code\": \"\",\r\n        \"bank_accounts\": [\r\n            {}\r\n        ],\r\n        \"legal_name\": \"Testing\",\r\n        \"brand_name\": \"Testing\",\r\n        \"registration_number\": \"\",\r\n        \"tax_number\": \"\"\r\n    },\r\n    \"transaction_data\": {\r\n        \"payment_method\": \"\",\r\n        \"flow\": \"payform\",\r\n        \"extra\": {\r\n            \"amount\": 1.0,\r\n            \"masked_pan\": \"GOOGLEPAY-REDIRECT\"\r\n        },\r\n        \"country\": \"\",\r\n        \"attempts\": [\r\n            {\r\n                \"client_ip\": \"183.83.53.41\",\r\n                \"type\": \"execute\",\r\n                \"payment_method\": \"GOOGLEPAY-REDIRECT\",\r\n                \"flow\": \"payform\",\r\n                \"successful\": true,\r\n                \"country\": \"GOOGLEPAY-REDIRECT\",\r\n                \"processing_time\": 1768115700,\r\n                \"extra\": {\r\n                    \"amount\": 1.0,\r\n                    \"masked_pan\": \"GOOGLEPAY-REDIRECT\"\r\n                }\r\n            }\r\n        ]\r\n    },\r\n    \"status\": \"PAYMENT_IN_PROCESS\",\r\n    \"status_history\": [\r\n        {\r\n            \"status\": \"created\",\r\n            \"timestamp\": 1768115700\r\n        },\r\n        {\r\n            \"status\": \"pending_execute\",\r\n            \"timestamp\": 1768115700\r\n        },\r\n        {\r\n            \"status\": \"payment_in_process\",\r\n            \"timestamp\": 1768115701\r\n        }\r\n    ],\r\n    \"is_test\": false,\r\n    \"brand_id\": \"59c5ed48-caf9-464a-ba54-26e1e02bc1bc\",\r\n    \"send_receipt\": false,\r\n    \"is_recurring_token\": false,\r\n    \"skip_capture\": false,\r\n    \"reference_generated\": \"PS363\",\r\n    \"issued\": \"2026-01-11\",\r\n    \"due\": 1768115700,\r\n    \"refund_upto\": 1783664101,\r\n    \"cc_descriptor\": \"\",\r\n    \"fraudScore\": \"0\",\r\n    \"trustScore\": \"1\",\r\n    \"extraFee\": \"0\",\r\n    \"pix_payload\": {},\r\n    \"payInDetails\": {},\r\n    \"paidOn\": 0,\r\n    \"receivedAmt\": 0.0,\r\n    \"taxAmount\": 0.0,\r\n    \"surcharge\": 0.0,\r\n    \"surchargeType\": \"\",\r\n    \"sessionId\": \"\",\r\n    \"refund_availability\": \"NONE\",\r\n    \"refundable_amount\": 1.0,\r\n    \"success_redirect\": \"https://your-redirect-url?issucces=true\",\r\n    \"pending_redirect\": \"https://your-redirect-url?ispending=true\",\r\n    \"failure_redirect\": \"https://your-redirect-url?isfailure=true\",\r\n    \"success_callback\": \"https://your-webhook-url\",\r\n    \"failure_callback\": \"https://your-webhook-url\"\r\n    \"platform\": \"API\",\r\n    \"created_from_ip\": \"183.83.53.41\",\r\n    \"checkout_url\": \"https://api.choicepay.ca/payments/deb852445bd4b0fa6c4587f652174ab9/\",\r\n    \"payoutProcess\": false\r\n}"
```


# Session

**OVERVIEW**

The `createSession` API is designed to initiate a payment session for a customer after their profile has been created via the **createCustomer** API. The session is automatically generated at the backend on the merchant’s checkout URL. This session allows the customer to continue with their transaction without having to manually interact with the session URL, and ensures the session remains active until the payment is completed or the session expires.

This API improves the user experience by reducing transaction failures and enhancing the overall payment process, thus reducing transaction churn rates.

### Mandatory Parameters

| Parameter | Type | Description | Example |
| --- | --- | --- | --- |
| customerId | String | The unique ID of the customer (generated from createCustomer). | 6731a609b6bb5a43ad66c4a6 |

### **Usage Flow**

1. **Customer completes the** **`createCustomer`** **API**: Once the customer is created via the `createCustomer` API, the merchant proceeds to call the `createSession` API to generate a session.

2. **Merchant sends** **`createSession`** **request**: The merchant sends a `POST` request to the `createSession` API with the customer’s `customerId` and the merchant’s `brandId`.

3. **Session created automatically on the checkout URL**: PaySecure creates the session and associates it with the merchant’s checkout page. This session remains active on the backend, allowing the customer to continue the payment process without interruption.

4. **Customer proceeds to checkout**: The customer is redirected to the checkout page as part of the merchant's payment flow, where the session is automatically validated. The session remains active for a set period, allowing the customer to complete the payment without needing to manually interact with the session URL.

5. **Session Expiry**: The session expires after the set expiration time (`expiryOn`), ensuring the payment process is completed within the defined window. Default is 15 mins from the creation time.

---


### **Benefits**

- **Seamless Checkout**: The session URL is automatically generated and active at the backend, ensuring a smoother and uninterrupted customer experience.

- **Reduced Transaction Failures**: By ensuring the session remains active during the payment process, the chances of transaction failures due to session timeouts are minimized.

- **Improved User Experience**: The customer does not need to click on a session URL or navigate away from the page, leading to faster and more secure payment processing.

:information_source: **Note** This endpoint does not require authentication.

```ts
async session(
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success14>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success14`](../../doc/models/success-14.md).

## Example Usage

```ts
try {
  const response = await apIsApi.session();

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
    if (error instanceof InvalidSessionError) {
      console.log(error.result);
    }
  }
}
```

## Example Response *(as JSON)*

```json
{
  "sessionUrl": "https://api.choicepay.ca/payment-session/6963533a0a18ea65153a81e7/",
  "brandId": "brand_id_value",
  "customerId": "69034a5a61b460084d20c23b",
  "sessionId": "6963533a0a18ea65153a81e7",
  "expiryOn": 1768117950,
  "createdOn": 1768117050
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`InvalidSessionError`](../../doc/models/invalid-session-error.md) |


# Get Status 5

This API tells you about all the details of a purchase (PayIn), including its history

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
async getStatus5(
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
  const response = await apIsApi.getStatus5(purchaseId);

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
"{\r\n    \"purchaseId\": \"69634df44549cbd3547ac750\",\r\n    \"client\": {\r\n        \"customerId\": \"NA\",\r\n        \"email\": \"rahultest@gmail.com\",\r\n        \"phone\": \"+91 9634088561\",\r\n        \"full_name\": \"Rahul Agarwal\",\r\n        \"date_of_birth\": \"1994-31-04\",\r\n        \"street_address\": \"10 New Burlington StreetApt. 214\",\r\n        \"country\": \"GB\",\r\n        \"city\": \"London\",\r\n        \"zip_code\": \"W1S 3BE\",\r\n        \"cc\": [],\r\n        \"bcc\": [],\r\n        \"stateCode\": \"RJ\"\r\n    },\r\n    \"updated_on\": 1768115701,\r\n    \"type\": \"purchase\",\r\n    \"paymentMethod\": \"GOOGLEPAY-REDIRECT\",\r\n    \"amountUnit\": \"MAJOR\",\r\n    \"errorMsg\": \"\",\r\n    \"errorCode\": \"NA\",\r\n    \"force_recurring\": false,\r\n    \"created_on\": 1768115700,\r\n    \"merchantRef\": \"69634df44549cbd3547ac750\",\r\n    \"purchase\": {\r\n        \"currency\": \"EUR\",\r\n        \"products\": [\r\n            {\r\n                \"name\": \"gaming cards\",\r\n                \"quantity\": 1.0,\r\n                \"price\": 1.0,\r\n                \"discount\": 0,\r\n                \"tax_percent\": \"0.00\"\r\n            }\r\n        ],\r\n        \"total\": 1.0,\r\n        \"requestAmount\": 1.0,\r\n        \"language\": \"en\",\r\n        \"notes\": \"\",\r\n        \"debt\": 0,\r\n        \"total_formatted\": 1.0,\r\n        \"taxAmount\": 0.0,\r\n        \"taxPercent\": 0.0,\r\n        \"request_client_details\": [],\r\n        \"email_message\": \"\"\r\n    },\r\n    \"payment\": {\r\n        \"is_outgoing\": false,\r\n        \"payment_type\": \"PURCHASE\",\r\n        \"amount\": 1.0,\r\n        \"currency\": \"EUR\",\r\n        \"net_amount\": 1.0,\r\n        \"fee_amount\": 0.0,\r\n        \"pending_amount\": 0.0,\r\n        \"pending_unfreeze_on\": null,\r\n        \"description\": \"\",\r\n        \"paid_on\": 1768115700,\r\n        \"remote_paid_on\": 1768115700\r\n    },\r\n    \"issuer_details\": {\r\n        \"website\": \"\",\r\n        \"legal_street_address\": \"\",\r\n        \"legal_country\": \"\",\r\n        \"legal_city\": \"\",\r\n        \"legal_zip_code\": \"\",\r\n        \"bank_accounts\": [\r\n            {}\r\n        ],\r\n        \"legal_name\": \"Testing\",\r\n        \"brand_name\": \"Testing\",\r\n        \"registration_number\": \"\",\r\n        \"tax_number\": \"\"\r\n    },\r\n    \"transaction_data\": {\r\n        \"payment_method\": \"\",\r\n        \"flow\": \"payform\",\r\n        \"extra\": {\r\n            \"amount\": 1.0,\r\n            \"masked_pan\": \"GOOGLEPAY-REDIRECT\"\r\n        },\r\n        \"country\": \"\",\r\n        \"attempts\": [\r\n            {\r\n                \"client_ip\": \"183.83.53.41\",\r\n                \"type\": \"execute\",\r\n                \"payment_method\": \"GOOGLEPAY-REDIRECT\",\r\n                \"flow\": \"payform\",\r\n                \"successful\": true,\r\n                \"country\": \"GOOGLEPAY-REDIRECT\",\r\n                \"processing_time\": 1768115700,\r\n                \"extra\": {\r\n                    \"amount\": 1.0,\r\n                    \"masked_pan\": \"GOOGLEPAY-REDIRECT\"\r\n                }\r\n            }\r\n        ]\r\n    },\r\n    \"status\": \"PAID\",\r\n    \"status_history\": [\r\n        {\r\n            \"status\": \"created\",\r\n            \"timestamp\": 1768115700\r\n        },\r\n        {\r\n            \"status\": \"pending_execute\",\r\n            \"timestamp\": 1768115700\r\n        },\r\n        {\r\n            \"status\": \"payment_in_process\",\r\n            \"timestamp\": 1768115701\r\n        },\r\n        {\r\n            \"status\": \"paid\",\r\n            \"timestamp\": 1768115701\r\n        }\r\n    ],\r\n    \"is_test\": false,\r\n    \"brand_id\": \"59c5ed48-caf9-464a-ba54-26e1e02bc1bc\",\r\n    \"send_receipt\": false,\r\n    \"is_recurring_token\": false,\r\n    \"skip_capture\": false,\r\n    \"reference_generated\": \"PS363\",\r\n    \"issued\": \"2026-01-11\",\r\n    \"due\": 1768115700,\r\n    \"refund_upto\": 1783664101,\r\n    \"cc_descriptor\": \"\",\r\n    \"fraudScore\": \"0\",\r\n    \"trustScore\": \"1\",\r\n    \"extraFee\": \"0\",\r\n    \"pix_payload\": {},\r\n    \"payInDetails\": {},\r\n    \"paidOn\": 0,\r\n    \"receivedAmt\": 0.0,\r\n    \"taxAmount\": 0.0,\r\n    \"surcharge\": 0.0,\r\n    \"surchargeType\": \"\",\r\n    \"sessionId\": \"\",\r\n    \"refund_availability\": \"NONE\",\r\n    \"refundable_amount\": 1.0,\r\n    \"success_redirect\": \"https://your-redirect-url?issucces=true\",\r\n    \"pending_redirect\": \"https://your-redirect-url?ispending=true\",\r\n    \"failure_redirect\": \"https://your-redirect-url?isfailure=true\",\r\n    \"success_callback\": \"https://your-webhook-url\",\r\n    \"failure_callback\": \"https://your-webhook-url\"\r\n    \"platform\": \"API\",\r\n    \"created_from_ip\": \"183.83.53.41\",\r\n    \"checkout_url\": \"https://api.choicepay.ca/payments/deb852445bd4b0fa6c4587f652174ab9/\",\r\n    \"payoutProcess\": false\r\n}"
```


# Purchases 1

To Initiate a payment, the very first call to make is `/purchases` with the required data in the request body.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.full_name | Conditional.  <br>But Recommended to pass the complete name of the client. Atleast 2 words recommended. |
| client.email | Conditional.  <br>But Recommended to pass a correct email id. |
| paymentMethod | Conditional.  <br>Mandatory if you are not using Paysecure Cashier. Else Non Mandatory.  <br>Value: APPLEPAY-REDIRECT |
| purchase.currency | Mandatory.  <br>ISO 4217 code for currency you want to send the transaction in. This should be 'BRL' for PIX. |
| purchase.products.name | Mandatory. |
| purchase.products.price | Mandatory.  <br>Price in decimal format upto 2 decimals.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
| brand_id | Mandatory.  <br>Obtain from Dashboard section of your merchant account login. |
| success_redirect | Mandatory.  <br>URL to send the user if the transactions is successful. |
| pending_redirect | Mandatory.  <br>URL to send the user if the transactions is in progress state. |
| failure_redirect | Mandatory  <br>URL to send the user if the transactions has failed. |

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

:information_source: **Note** This endpoint does not require authentication.

```ts
async purchases1(
  body: PurchasesRequest6,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchasesRequest6`](../../doc/models/purchases-request-6.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const body: PurchasesRequest6 = {
  client: {
    email: 'rahultest@gmail.com',
    streetAddress: '10 New Burlington StreetApt. 214',
    city: 'London',
    fullName: 'Rahul Agarwal',
    zipCode: 'W1S 3BE',
    country: 'GB',
    dateOfBirth: '1994-31-04',
    stateCode: 'RJ',
    phone: '+91 9634088561',
  },
  purchase: {
    currency: 'EUR',
    products: [
      {
        name: 'gaming cards ',
        price: 10,
      }
    ],
  },
  brandId: 'your-brandid',
  paymentMethod: 'APPLEPAY-REDIRECT',
  successRedirect: 'https://your-redirect-url?issucces=true',
  pendingRedirect: 'https://your-redirect-url?ispending=true',
  failureRedirect: 'https://your-redirect-url?isfailure=true',
  successCallback: 'https://your-webhook-url',
  failureCallback: 'https://your-webhook-url',
};

try {
  const response = await apIsApi.purchases1(body);

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
"{\r\n    \"purchaseId\": \"69634df44549cbd3547ac750\",\r\n    \"client\": {\r\n        \"customerId\": \"NA\",\r\n        \"email\": \"rahultest@gmail.com\",\r\n        \"phone\": \"+91 9634088561\",\r\n        \"full_name\": \"Rahul Agarwal\",\r\n        \"date_of_birth\": \"1994-31-04\",\r\n        \"street_address\": \"10 New Burlington StreetApt. 214\",\r\n        \"country\": \"GB\",\r\n        \"city\": \"London\",\r\n        \"zip_code\": \"W1S 3BE\",\r\n        \"cc\": [],\r\n        \"bcc\": [],\r\n        \"stateCode\": \"RJ\"\r\n    },\r\n    \"updated_on\": 1768115701,\r\n    \"type\": \"purchase\",\r\n    \"paymentMethod\": \"APPLEPAY-REDIRECT\",\r\n    \"amountUnit\": \"MAJOR\",\r\n    \"errorMsg\": \"\",\r\n    \"errorCode\": \"NA\",\r\n    \"force_recurring\": false,\r\n    \"created_on\": 1768115700,\r\n    \"merchantRef\": \"69634df44549cbd3547ac750\",\r\n    \"purchase\": {\r\n        \"currency\": \"EUR\",\r\n        \"products\": [\r\n            {\r\n                \"name\": \"gaming cards\",\r\n                \"quantity\": 1.0,\r\n                \"price\": 1.0,\r\n                \"discount\": 0,\r\n                \"tax_percent\": \"0.00\"\r\n            }\r\n        ],\r\n        \"total\": 1.0,\r\n        \"requestAmount\": 1.0,\r\n        \"language\": \"en\",\r\n        \"notes\": \"\",\r\n        \"debt\": 0,\r\n        \"total_formatted\": 1.0,\r\n        \"taxAmount\": 0.0,\r\n        \"taxPercent\": 0.0,\r\n        \"request_client_details\": [],\r\n        \"email_message\": \"\"\r\n    },\r\n    \"payment\": {\r\n        \"is_outgoing\": false,\r\n        \"payment_type\": \"PURCHASE\",\r\n        \"amount\": 1.0,\r\n        \"currency\": \"EUR\",\r\n        \"net_amount\": 1.0,\r\n        \"fee_amount\": 0.0,\r\n        \"pending_amount\": 0.0,\r\n        \"pending_unfreeze_on\": null,\r\n        \"description\": \"\",\r\n        \"paid_on\": 1768115700,\r\n        \"remote_paid_on\": 1768115700\r\n    },\r\n    \"issuer_details\": {\r\n        \"website\": \"\",\r\n        \"legal_street_address\": \"\",\r\n        \"legal_country\": \"\",\r\n        \"legal_city\": \"\",\r\n        \"legal_zip_code\": \"\",\r\n        \"bank_accounts\": [\r\n            {}\r\n        ],\r\n        \"legal_name\": \"Testing\",\r\n        \"brand_name\": \"Testing\",\r\n        \"registration_number\": \"\",\r\n        \"tax_number\": \"\"\r\n    },\r\n    \"transaction_data\": {\r\n        \"payment_method\": \"\",\r\n        \"flow\": \"payform\",\r\n        \"extra\": {\r\n            \"amount\": 1.0,\r\n            \"masked_pan\": \"APPLEPAY-REDIRECT\"\r\n        },\r\n        \"country\": \"\",\r\n        \"attempts\": [\r\n            {\r\n                \"client_ip\": \"183.83.53.41\",\r\n                \"type\": \"execute\",\r\n                \"payment_method\": \"APPLEPAY-REDIRECT\",\r\n                \"flow\": \"payform\",\r\n                \"successful\": true,\r\n                \"country\": \"APPLEPAY-REDIRECT\",\r\n                \"processing_time\": 1768115700,\r\n                \"extra\": {\r\n                    \"amount\": 1.0,\r\n                    \"masked_pan\": \"APPLEPAY-REDIRECT\"\r\n                }\r\n            }\r\n        ]\r\n    },\r\n    \"status\": \"PAYMENT_IN_PROCESS\",\r\n    \"status_history\": [\r\n        {\r\n            \"status\": \"created\",\r\n            \"timestamp\": 1768115700\r\n        },\r\n        {\r\n            \"status\": \"pending_execute\",\r\n            \"timestamp\": 1768115700\r\n        },\r\n        {\r\n            \"status\": \"payment_in_process\",\r\n            \"timestamp\": 1768115701\r\n        }\r\n    ],\r\n    \"is_test\": false,\r\n    \"brand_id\": \"59c5ed48-caf9-464a-ba54-26e1e02bc1bc\",\r\n    \"send_receipt\": false,\r\n    \"is_recurring_token\": false,\r\n    \"skip_capture\": false,\r\n    \"reference_generated\": \"PS363\",\r\n    \"issued\": \"2026-01-11\",\r\n    \"due\": 1768115700,\r\n    \"refund_upto\": 1783664101,\r\n    \"cc_descriptor\": \"\",\r\n    \"fraudScore\": \"0\",\r\n    \"trustScore\": \"1\",\r\n    \"extraFee\": \"0\",\r\n    \"pix_payload\": {},\r\n    \"payInDetails\": {},\r\n    \"paidOn\": 0,\r\n    \"receivedAmt\": 0.0,\r\n    \"taxAmount\": 0.0,\r\n    \"surcharge\": 0.0,\r\n    \"surchargeType\": \"\",\r\n    \"sessionId\": \"\",\r\n    \"refund_availability\": \"NONE\",\r\n    \"refundable_amount\": 1.0,\r\n    \"success_redirect\": \"https://your-redirect-url?issucces=true\",\r\n    \"pending_redirect\": \"https://your-redirect-url?ispending=true\",\r\n    \"failure_redirect\": \"https://your-redirect-url?isfailure=true\",\r\n    \"success_callback\": \"https://your-webhook-url\",\r\n    \"failure_callback\": \"https://your-webhook-url\"\r\n    \"platform\": \"API\",\r\n    \"created_from_ip\": \"183.83.53.41\",\r\n    \"checkout_url\": \"https://api.choicepay.ca/payments/deb852445bd4b0fa6c4587f652174ab9/\",\r\n    \"payoutProcess\": false\r\n}"
```


# Session 1

**OVERVIEW**

The `createSession` API is designed to initiate a payment session for a customer after their profile has been created via the **createCustomer** API. The session is automatically generated at the backend on the merchant’s checkout URL. This session allows the customer to continue with their transaction without having to manually interact with the session URL, and ensures the session remains active until the payment is completed or the session expires.

This API improves the user experience by reducing transaction failures and enhancing the overall payment process, thus reducing transaction churn rates.

### Mandatory Parameters

| Parameter | Type | Description | Example |
| --- | --- | --- | --- |
| customerId | String | The unique ID of the customer (generated from createCustomer). | 6731a609b6bb5a43ad66c4a6 |

### **Usage Flow**

1. **Customer completes the** **`createCustomer`** **API**: Once the customer is created via the `createCustomer` API, the merchant proceeds to call the `createSession` API to generate a session.

2. **Merchant sends** **`createSession`** **request**: The merchant sends a `POST` request to the `createSession` API with the customer’s `customerId` and the merchant’s `brandId`.

3. **Session created automatically on the checkout URL**: PaySecure creates the session and associates it with the merchant’s checkout page. This session remains active on the backend, allowing the customer to continue the payment process without interruption.

4. **Customer proceeds to checkout**: The customer is redirected to the checkout page as part of the merchant's payment flow, where the session is automatically validated. The session remains active for a set period, allowing the customer to complete the payment without needing to manually interact with the session URL.

5. **Session Expiry**: The session expires after the set expiration time (`expiryOn`), ensuring the payment process is completed within the defined window. Default is 15 mins from the creation time.

---


### **Benefits**

- **Seamless Checkout**: The session URL is automatically generated and active at the backend, ensuring a smoother and uninterrupted customer experience.

- **Reduced Transaction Failures**: By ensuring the session remains active during the payment process, the chances of transaction failures due to session timeouts are minimized.

- **Improved User Experience**: The customer does not need to click on a session URL or navigate away from the page, leading to faster and more secure payment processing.

:information_source: **Note** This endpoint does not require authentication.

```ts
async session1(
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success14>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success14`](../../doc/models/success-14.md).

## Example Usage

```ts
try {
  const response = await apIsApi.session1();

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
    if (error instanceof InvalidSessionError) {
      console.log(error.result);
    }
  }
}
```

## Example Response *(as JSON)*

```json
{
  "sessionUrl": "https://api.choicepay.ca/payment-session/6963533a0a18ea65153a81e7/",
  "brandId": "brand_id_value",
  "customerId": "69034a5a61b460084d20c23b",
  "sessionId": "6963533a0a18ea65153a81e7",
  "expiryOn": 1768117950,
  "createdOn": 1768117050
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`InvalidSessionError`](../../doc/models/invalid-session-error.md) |


# Get Status 1

This API tells you about all the details of a purchase (PayIn), including its history

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
  const response = await apIsApi.getStatus1(purchaseId);

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
"{\r\n    \"purchaseId\": \"69634df44549cbd3547ac750\",\r\n    \"client\": {\r\n        \"customerId\": \"NA\",\r\n        \"email\": \"rahultest@gmail.com\",\r\n        \"phone\": \"+91 9634088561\",\r\n        \"full_name\": \"Rahul Agarwal\",\r\n        \"date_of_birth\": \"1994-31-04\",\r\n        \"street_address\": \"10 New Burlington StreetApt. 214\",\r\n        \"country\": \"GB\",\r\n        \"city\": \"London\",\r\n        \"zip_code\": \"W1S 3BE\",\r\n        \"cc\": [],\r\n        \"bcc\": [],\r\n        \"stateCode\": \"RJ\"\r\n    },\r\n    \"updated_on\": 1768115701,\r\n    \"type\": \"purchase\",\r\n    \"paymentMethod\": \"APPLEPAY-REDIRECT\",\r\n    \"amountUnit\": \"MAJOR\",\r\n    \"errorMsg\": \"\",\r\n    \"errorCode\": \"NA\",\r\n    \"force_recurring\": false,\r\n    \"created_on\": 1768115700,\r\n    \"merchantRef\": \"69634df44549cbd3547ac750\",\r\n    \"purchase\": {\r\n        \"currency\": \"EUR\",\r\n        \"products\": [\r\n            {\r\n                \"name\": \"gaming cards\",\r\n                \"quantity\": 1.0,\r\n                \"price\": 1.0,\r\n                \"discount\": 0,\r\n                \"tax_percent\": \"0.00\"\r\n            }\r\n        ],\r\n        \"total\": 1.0,\r\n        \"requestAmount\": 1.0,\r\n        \"language\": \"en\",\r\n        \"notes\": \"\",\r\n        \"debt\": 0,\r\n        \"total_formatted\": 1.0,\r\n        \"taxAmount\": 0.0,\r\n        \"taxPercent\": 0.0,\r\n        \"request_client_details\": [],\r\n        \"email_message\": \"\"\r\n    },\r\n    \"payment\": {\r\n        \"is_outgoing\": false,\r\n        \"payment_type\": \"PURCHASE\",\r\n        \"amount\": 1.0,\r\n        \"currency\": \"EUR\",\r\n        \"net_amount\": 1.0,\r\n        \"fee_amount\": 0.0,\r\n        \"pending_amount\": 0.0,\r\n        \"pending_unfreeze_on\": null,\r\n        \"description\": \"\",\r\n        \"paid_on\": 1768115700,\r\n        \"remote_paid_on\": 1768115700\r\n    },\r\n    \"issuer_details\": {\r\n        \"website\": \"\",\r\n        \"legal_street_address\": \"\",\r\n        \"legal_country\": \"\",\r\n        \"legal_city\": \"\",\r\n        \"legal_zip_code\": \"\",\r\n        \"bank_accounts\": [\r\n            {}\r\n        ],\r\n        \"legal_name\": \"Testing\",\r\n        \"brand_name\": \"Testing\",\r\n        \"registration_number\": \"\",\r\n        \"tax_number\": \"\"\r\n    },\r\n    \"transaction_data\": {\r\n        \"payment_method\": \"\",\r\n        \"flow\": \"payform\",\r\n        \"extra\": {\r\n            \"amount\": 1.0,\r\n            \"masked_pan\": \"APPLEPAY-REDIRECT\"\r\n        },\r\n        \"country\": \"\",\r\n        \"attempts\": [\r\n            {\r\n                \"client_ip\": \"183.83.53.41\",\r\n                \"type\": \"execute\",\r\n                \"payment_method\": \"APPLEPAY-REDIRECT\",\r\n                \"flow\": \"payform\",\r\n                \"successful\": true,\r\n                \"country\": \"APPLEPAY-REDIRECT\",\r\n                \"processing_time\": 1768115700,\r\n                \"extra\": {\r\n                    \"amount\": 1.0,\r\n                    \"masked_pan\": \"APPLEPAY-REDIRECT\"\r\n                }\r\n            }\r\n        ]\r\n    },\r\n    \"status\": \"PAID\",\r\n    \"status_history\": [\r\n        {\r\n            \"status\": \"created\",\r\n            \"timestamp\": 1768115700\r\n        },\r\n        {\r\n            \"status\": \"pending_execute\",\r\n            \"timestamp\": 1768115700\r\n        },\r\n        {\r\n            \"status\": \"payment_in_process\",\r\n            \"timestamp\": 1768115701\r\n        },\r\n        {\r\n            \"status\": \"paid\",\r\n            \"timestamp\": 1768115701\r\n        }\r\n    ],\r\n    \"is_test\": false,\r\n    \"brand_id\": \"59c5ed48-caf9-464a-ba54-26e1e02bc1bc\",\r\n    \"send_receipt\": false,\r\n    \"is_recurring_token\": false,\r\n    \"skip_capture\": false,\r\n    \"reference_generated\": \"PS363\",\r\n    \"issued\": \"2026-01-11\",\r\n    \"due\": 1768115700,\r\n    \"refund_upto\": 1783664101,\r\n    \"cc_descriptor\": \"\",\r\n    \"fraudScore\": \"0\",\r\n    \"trustScore\": \"1\",\r\n    \"extraFee\": \"0\",\r\n    \"pix_payload\": {},\r\n    \"payInDetails\": {},\r\n    \"paidOn\": 0,\r\n    \"receivedAmt\": 0.0,\r\n    \"taxAmount\": 0.0,\r\n    \"surcharge\": 0.0,\r\n    \"surchargeType\": \"\",\r\n    \"sessionId\": \"\",\r\n    \"refund_availability\": \"NONE\",\r\n    \"refundable_amount\": 1.0,\r\n    \"success_redirect\": \"https://your-redirect-url?issucces=true\",\r\n    \"pending_redirect\": \"https://your-redirect-url?ispending=true\",\r\n    \"failure_redirect\": \"https://your-redirect-url?isfailure=true\",\r\n    \"success_callback\": \"https://your-webhook-url\",\r\n    \"failure_callback\": \"https://your-webhook-url\"\r\n    \"platform\": \"API\",\r\n    \"created_from_ip\": \"183.83.53.41\",\r\n    \"checkout_url\": \"https://api.choicepay.ca/payments/deb852445bd4b0fa6c4587f652174ab9/\",\r\n    \"payoutProcess\": false\r\n}"
```


# Purchases Encrypted Flow

To process a Google Pay transaction, a Purchase must first be created using the /purchases API. The Google Pay token must be included in the request under extraParam.googlepay_param.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.full_name | Conditional.  <br>But Recommended to pass the complete name of the client. Atleast 2 words recommended. |
| client.email | Conditional.  <br>But Recommended to pass a correct email id. |
| paymentMethod | Conditional.  <br>Mandatory if you are not using Paysecure Cashier. Else Non Mandatory.  <br>Value: GOOGLEPAY |
| purchase.currency | Mandatory.  <br>ISO 4217 code for currency you want to send the transaction in. This should be 'BRL' for PIX. |
| purchase.products.name | Mandatory. |
| purchase.products.price | Mandatory.  <br>Price in decimal format upto 2 decimals.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
| brand_id | Mandatory.  <br>Obtain from Dashboard section of your merchant account login. |
| success_redirect | Mandatory.  <br>URL to send the user if the transactions is successful. |
| pending_redirect | Mandatory.  <br>URL to send the user if the transactions is in progress state. |
| failure_redirect | Mandatory  <br>URL to send the user if the transactions has failed. |

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

### Flow Diagram:

<img src="https://content.pstmn.io/2dd13473-b015-4a40-b71a-542585919bcc/RW5jcnlwdGVkIEZsb3cucG5n">


:information_source: **Note** This endpoint does not require authentication.

```ts
async purchasesEncryptedFlow(
  body: PurchasesEncryptedFlowRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PurchaseSuccess4>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchasesEncryptedFlowRequest`](../../doc/models/purchases-encrypted-flow-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchaseSuccess4`](../../doc/models/purchase-success-4.md).

## Example Usage

```ts
const body: PurchasesEncryptedFlowRequest = {
  client: {
    customerId: 'NA',
    email: 'himanshu1@paysecure.net',
    fullName: 'OpHM',
    dateOfBirth: '1800-01-01',
    streetAddress: 'SB-124',
    country: 'BR',
    city: 'DLJPR',
    zipCode: '110001',
    cc: [],
    bcc: [],
    stateCode: 'DL',
  },
  purchase: {
    currency: 'EUR',
    products: [
      {
        name: 'e-commerce',
        price: '10',
      }
    ],
  },
  paymentMethod: 'GOOGLEPAY',
  brandId: 'f1764688-d991-481b-be63-9ee7f33dcd31',
  successRedirect: 'https://google.com/',
  pendingRedirect: 'https://paysecure.net',
  failureRedirect: 'https://facebook.com/',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  extraParam: {
    googlepayParam: {
      googleMerchantId: 'merchant:1234567890',
      googlepayEncryptedPayload: '{"signature":"MEUCIQC...","intermediateSigningKey":{...},"protocolVersion":"ECv2","signedMessage":"{...}"}',
    },
  },
};

try {
  const response = await apIsApi.purchasesEncryptedFlow(body);

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
  "purchaseId": "69cce01f5bae56fd5547a993",
  "client": {
    "customerId": "NA",
    "email": "himanshu1@paysecure.net",
    "full_name": "OpHM",
    "date_of_birth": "1800-01-01",
    "street_address": "SB-124",
    "country": "BR",
    "city": "DLJPR",
    "zip_code": "110001",
    "cc": [],
    "bcc": [],
    "stateCode": "DL"
  },
  "updated_on": 1775034399,
  "type": "purchase",
  "paymentMethod": "GOOGLEPAY",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "errorCode": "NA",
  "force_recurring": false,
  "created_on": 1775034399,
  "merchantRef": "69cce01f5bae56fd5547a993",
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "name": "e-commerce",
        "quantity": 1.0,
        "price": 10.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 10.0,
    "requestAmount": 10.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "taxAmount": 0.0,
    "taxPercent": 0.0,
    "request_client_details": [],
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
    "legal_name": "Omega Pixel",
    "brand_name": "Omega Pixel",
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
      "timestamp": 1775034399
    }
  ],
  "is_test": false,
  "brand_id": "f1764688-d991-481b-be63-9ee7f33dcd31",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS1032",
  "issued": "2026-04-01",
  "due": 1775034399,
  "refund_upto": 0,
  "cc_descriptor": "",
  "fraudScore": "NA",
  "trustScore": "NA",
  "extraFee": "0",
  "paidOn": 0,
  "receivedAmt": 0.0,
  "taxAmount": 0.0,
  "surcharge": 0.0,
  "surchargeType": "",
  "sessionId": "",
  "refund_availability": "NONE",
  "refundable_amount": 0.0,
  "success_redirect": "https://google.com/",
  "failure_redirect": "https://facebook.com/",
  "pending_redirect": "https://paysecure.net",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.com",
  "failure_callback": "https://your.failure.callback.com",
  "platform": "API",
  "created_from_ip": "103.80.161.238",
  "checkout_url": "https://api.choicepay.ca/payments/6b5a5977ac8e022facb31f3346f61ed0/",
  "direct_post_url": "https://api.choicepay.ca/api/v1/p/69cce01f5bae56fd5547a993/",
  "payoutProcess": false
}
```


# Purchases Decrypted Flow

To process a Google Pay transaction, a Purchase must first be created using the /purchases API. The Google Pay token must be included in the request under extraParam.googlepay_param.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.full_name | Conditional.  <br>But Recommended to pass the complete name of the client. Atleast 2 words recommended. |
| client.email | Conditional.  <br>But Recommended to pass a correct email id. |
| paymentMethod | Conditional.  <br>Mandatory if you are not using Paysecure Cashier. Else Non Mandatory.  <br>Value: GOOGLEPAY |
| purchase.currency | Mandatory.  <br>ISO 4217 code for currency you want to send the transaction in. This should be 'BRL' for PIX. |
| purchase.products.name | Mandatory. |
| purchase.products.price | Mandatory.  <br>Price in decimal format upto 2 decimals.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
| brand_id | Mandatory.  <br>Obtain from Dashboard section of your merchant account login. |
| success_redirect | Mandatory.  <br>URL to send the user if the transactions is successful. |
| pending_redirect | Mandatory.  <br>URL to send the user if the transactions is in progress state. |
| failure_redirect | Mandatory  <br>URL to send the user if the transactions has failed. |

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

### Flow Diagram:

<img src="https://content.pstmn.io/8d726da8-02f8-49a4-a3a9-765cd3e1dd9a/RGVjcnlwdGVkIEZsb3cucG5n">


:information_source: **Note** This endpoint does not require authentication.

```ts
async purchasesDecryptedFlow(
  body: PurchasesDecryptedFlowRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PurchaseSuccess4>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchasesDecryptedFlowRequest`](../../doc/models/purchases-decrypted-flow-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchaseSuccess4`](../../doc/models/purchase-success-4.md).

## Example Usage

```ts
const body: PurchasesDecryptedFlowRequest = {
  client: {
    customerId: 'NA',
    email: 'himanshu1@paysecure.net',
    fullName: 'OpHM',
    dateOfBirth: '1800-01-01',
    streetAddress: 'SB-124',
    country: 'BR',
    city: 'DLJPR',
    zipCode: '110001',
    cc: [],
    bcc: [],
    stateCode: 'DL',
  },
  purchase: {
    currency: 'EUR',
    products: [
      {
        name: 'e-commerce',
        price: '10',
      }
    ],
  },
  paymentMethod: 'GOOGLEPAY',
  brandId: 'f1764688-d991-481b-be63-9ee7f33dcd31',
  successRedirect: 'https://google.com/',
  pendingRedirect: 'https://paysecure.net',
  failureRedirect: 'https://facebook.com/',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  extraParam: {
    googlepayParam: {
      googleMerchantId: 'merchant:1234567890',
      googlepayDecryptedPayload: {
        messageExpiration: '1735689600000',
        messageId: 'AH2EjtfkYz...',
        paymentMethod: 'CARD',
        paymentMethodDetails: {
          pan: '4111111111111111',
          expirationMonth: 12,
          expirationYear: 2027,
          authMethod: 'CRYPTOGRAM_3DS',
          cryptogram: 'AgAAAAAABk4D...',
          eciIndicator: '05',
        },
        gatewayMerchantId: 'your_gateway_merchant_id',
      },
    },
  },
};

try {
  const response = await apIsApi.purchasesDecryptedFlow(body);

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
  "purchaseId": "69cce01f5bae56fd5547a993",
  "client": {
    "customerId": "NA",
    "email": "himanshu1@paysecure.net",
    "full_name": "OpHM",
    "date_of_birth": "1800-01-01",
    "street_address": "SB-124",
    "country": "BR",
    "city": "DLJPR",
    "zip_code": "110001",
    "cc": [],
    "bcc": [],
    "stateCode": "DL"
  },
  "updated_on": 1775034399,
  "type": "purchase",
  "paymentMethod": "GOOGLEPAY",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "errorCode": "NA",
  "force_recurring": false,
  "created_on": 1775034399,
  "merchantRef": "69cce01f5bae56fd5547a993",
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "name": "e-commerce",
        "quantity": 1.0,
        "price": 10.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 10.0,
    "requestAmount": 10.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "taxAmount": 0.0,
    "taxPercent": 0.0,
    "request_client_details": [],
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
    "legal_name": "Omega Pixel",
    "brand_name": "Omega Pixel",
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
      "timestamp": 1775034399
    }
  ],
  "is_test": false,
  "brand_id": "f1764688-d991-481b-be63-9ee7f33dcd31",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS1032",
  "issued": "2026-04-01",
  "due": 1775034399,
  "refund_upto": 0,
  "cc_descriptor": "",
  "fraudScore": "NA",
  "trustScore": "NA",
  "extraFee": "0",
  "paidOn": 0,
  "receivedAmt": 0.0,
  "taxAmount": 0.0,
  "surcharge": 0.0,
  "surchargeType": "",
  "sessionId": "",
  "refund_availability": "NONE",
  "refundable_amount": 0.0,
  "success_redirect": "https://google.com/",
  "failure_redirect": "https://facebook.com/",
  "pending_redirect": "https://paysecure.net",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.com",
  "failure_callback": "https://your.failure.callback.com",
  "platform": "API",
  "created_from_ip": "103.80.161.238",
  "checkout_url": "https://api.choicepay.ca/payments/6b5a5977ac8e022facb31f3346f61ed0/",
  "direct_post_url": "https://api.choicepay.ca/api/v1/p/69cce01f5bae56fd5547a993/",
  "payoutProcess": false
}
```


# Get Status 2

This API tells you about all the details of a purchase (PayIn), including its history

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
async getStatus2(
  purchaseId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PurchaseSuccess4>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchaseSuccess4`](../../doc/models/purchase-success-4.md).

## Example Usage

```ts
const purchaseId = 'purchaseId2';

try {
  const response = await apIsApi.getStatus2(purchaseId);

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
  "purchaseId": "69cce01f5bae56fd5547a993",
  "client": {
    "customerId": "NA",
    "email": "himanshu1@paysecure.net",
    "full_name": "OpHM",
    "date_of_birth": "1800-01-01",
    "street_address": "SB-124",
    "country": "BR",
    "city": "DLJPR",
    "zip_code": "110001",
    "cc": [],
    "bcc": [],
    "stateCode": "DL"
  },
  "updated_on": 1775034399,
  "type": "purchase",
  "paymentMethod": "GOOGLEPAY",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "errorCode": "NA",
  "force_recurring": false,
  "created_on": 1775034399,
  "merchantRef": "69cce01f5bae56fd5547a993",
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "name": "e-commerce",
        "quantity": 1.0,
        "price": 10.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 10.0,
    "requestAmount": 10.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "taxAmount": 0.0,
    "taxPercent": 0.0,
    "request_client_details": [],
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
    "legal_name": "Omega Pixel",
    "brand_name": "Omega Pixel",
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
      "timestamp": 1775034399
    }
  ],
  "is_test": false,
  "brand_id": "f1764688-d991-481b-be63-9ee7f33dcd31",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS1032",
  "issued": "2026-04-01",
  "due": 1775034399,
  "refund_upto": 0,
  "cc_descriptor": "",
  "fraudScore": "NA",
  "trustScore": "NA",
  "extraFee": "0",
  "paidOn": 0,
  "receivedAmt": 0.0,
  "taxAmount": 0.0,
  "surcharge": 0.0,
  "surchargeType": "",
  "sessionId": "",
  "refund_availability": "NONE",
  "refundable_amount": 0.0,
  "success_redirect": "https://google.com/",
  "failure_redirect": "https://facebook.com/",
  "pending_redirect": "https://paysecure.net",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.com",
  "failure_callback": "https://your.failure.callback.com",
  "platform": "API",
  "created_from_ip": "103.80.161.238",
  "checkout_url": "https://api.choicepay.ca/payments/6b5a5977ac8e022facb31f3346f61ed0/",
  "direct_post_url": "https://api.choicepay.ca/api/v1/p/69cce01f5bae56fd5547a993/",
  "payoutProcess": false
}
```


# Purchases Encrypted Flow 1

To process an Apple Pay transaction, a Purchase must be created using the /purchases API. The Apple Pay token must be included under extraParam.applepay_param.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.full_name | Conditional.  <br>But Recommended to pass the complete name of the client. Atleast 2 words recommended. |
| client.email | Conditional.  <br>But Recommended to pass a correct email id. |
| paymentMethod | Conditional.  <br>Mandatory if you are not using Paysecure Cashier. Else Non Mandatory.  <br>Value: APPLEPAY |
| purchase.currency | Mandatory.  <br>ISO 4217 code for currency you want to send the transaction in. This should be 'BRL' for PIX. |
| purchase.products.name | Mandatory. |
| purchase.products.price | Mandatory.  <br>Price in decimal format upto 2 decimals.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
| brand_id | Mandatory.  <br>Obtain from Dashboard section of your merchant account login. |
| success_redirect | Mandatory.  <br>URL to send the user if the transactions is successful. |
| pending_redirect | Mandatory.  <br>URL to send the user if the transactions is in progress state. |
| failure_redirect | Mandatory  <br>URL to send the user if the transactions has failed. |

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

:information_source: **Note** This endpoint does not require authentication.

```ts
async purchasesEncryptedFlow1(
  body: PurchasesEncryptedFlowRequest1,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PurchaseSuccess4>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchasesEncryptedFlowRequest1`](../../doc/models/purchases-encrypted-flow-request-1.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchaseSuccess4`](../../doc/models/purchase-success-4.md).

## Example Usage

```ts
const body: PurchasesEncryptedFlowRequest1 = {
  client: {
    email: 'customer@example.com',
  },
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'Product',
        price: '10.00',
      }
    ],
  },
  paymentMethod: 'APPLEPAY',
  brandId: 'your_brand_id',
  successRedirect: 'https://success.com',
  pendingRedirect: 'https://pending.com',
  failureRedirect: 'https://failure.com',
  extraParam: {
    applepayParam: {
      applepayToken: {
        version: 'EC_v1',
        data: '...',
        signature: '...',
        header: {
          ephemeralPublicKey: '...',
          publicKeyHash: '...',
          transactionId: '...',
        },
      },
    },
  },
};

try {
  const response = await apIsApi.purchasesEncryptedFlow1(body);

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
  "purchaseId": "69cce01f5bae56fd5547a993",
  "client": {
    "customerId": "NA",
    "email": "himanshu1@paysecure.net",
    "full_name": "OpHM",
    "date_of_birth": "1800-01-01",
    "street_address": "SB-124",
    "country": "BR",
    "city": "DLJPR",
    "zip_code": "110001",
    "cc": [],
    "bcc": [],
    "stateCode": "DL"
  },
  "updated_on": 1775034399,
  "type": "purchase",
  "paymentMethod": "APPLEPAY",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "errorCode": "NA",
  "force_recurring": false,
  "created_on": 1775034399,
  "merchantRef": "69cce01f5bae56fd5547a993",
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "name": "e-commerce",
        "quantity": 1.0,
        "price": 10.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 10.0,
    "requestAmount": 10.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "taxAmount": 0.0,
    "taxPercent": 0.0,
    "request_client_details": [],
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
    "legal_name": "Omega Pixel",
    "brand_name": "Omega Pixel",
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
      "timestamp": 1775034399
    }
  ],
  "is_test": false,
  "brand_id": "f1764688-d991-481b-be63-9ee7f33dcd31",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS1032",
  "issued": "2026-04-01",
  "due": 1775034399,
  "refund_upto": 0,
  "cc_descriptor": "",
  "fraudScore": "NA",
  "trustScore": "NA",
  "extraFee": "0",
  "paidOn": 0,
  "receivedAmt": 0.0,
  "taxAmount": 0.0,
  "surcharge": 0.0,
  "surchargeType": "",
  "sessionId": "",
  "refund_availability": "NONE",
  "refundable_amount": 0.0,
  "success_redirect": "https://google.com/",
  "failure_redirect": "https://facebook.com/",
  "pending_redirect": "https://paysecure.net",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.com",
  "failure_callback": "https://your.failure.callback.com",
  "platform": "API",
  "created_from_ip": "103.80.161.238",
  "checkout_url": "https://api.choicepay.ca/payments/6b5a5977ac8e022facb31f3346f61ed0/",
  "direct_post_url": "https://api.choicepay.ca/api/v1/p/69cce01f5bae56fd5547a993/",
  "payoutProcess": false
}
```


# Purchases Decrypted Flow 1

To process an Apple Pay transaction, a Purchase must be created using the /purchases API. The Apple Pay token must be included under extraParam.applepay_param.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.full_name | Conditional.  <br>But Recommended to pass the complete name of the client. Atleast 2 words recommended. |
| client.email | Conditional.  <br>But Recommended to pass a correct email id. |
| paymentMethod | Conditional.  <br>Mandatory if you are not using Paysecure Cashier. Else Non Mandatory.  <br>Value: APPLEPAY |
| purchase.currency | Mandatory.  <br>ISO 4217 code for currency you want to send the transaction in. This should be 'BRL' for PIX. |
| purchase.products.name | Mandatory. |
| purchase.products.price | Mandatory.  <br>Price in decimal format upto 2 decimals.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
| brand_id | Mandatory.  <br>Obtain from Dashboard section of your merchant account login. |
| success_redirect | Mandatory.  <br>URL to send the user if the transactions is successful. |
| pending_redirect | Mandatory.  <br>URL to send the user if the transactions is in progress state. |
| failure_redirect | Mandatory  <br>URL to send the user if the transactions has failed. |

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

:information_source: **Note** This endpoint does not require authentication.

```ts
async purchasesDecryptedFlow1(
  body: PurchasesDecryptedFlowRequest1,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PurchaseSuccess4>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchasesDecryptedFlowRequest1`](../../doc/models/purchases-decrypted-flow-request-1.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchaseSuccess4`](../../doc/models/purchase-success-4.md).

## Example Usage

```ts
const body: PurchasesDecryptedFlowRequest1 = {
  client: {
    email: 'customer@example.com',
  },
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'Product',
        price: '10.00',
      }
    ],
  },
  paymentMethod: 'APPLEPAY',
  brandId: 'your_brand_id',
  successRedirect: 'https://success.com',
  pendingRedirect: 'https://pending.com',
  failureRedirect: 'https://failure.com',
  extraParam: {
    applepayParam: {
      applepayDecryptedPayload: {
        applicationPrimaryAccountNumber: '4111111111111111',
        applicationExpirationDate: '2712',
        currencyCode: '840',
        transactionAmount: 1000,
        deviceManufacturerIdentifier: '040010030273',
        paymentDataType: '3DSecure',
        paymentData: {
          onlinePaymentCryptogram: 'AgAAAAAABk4D...',
          eciIndicator: '05',
        },
      },
    },
  },
};

try {
  const response = await apIsApi.purchasesDecryptedFlow1(body);

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
  "purchaseId": "69cce01f5bae56fd5547a993",
  "client": {
    "customerId": "NA",
    "email": "himanshu1@paysecure.net",
    "full_name": "OpHM",
    "date_of_birth": "1800-01-01",
    "street_address": "SB-124",
    "country": "BR",
    "city": "DLJPR",
    "zip_code": "110001",
    "cc": [],
    "bcc": [],
    "stateCode": "DL"
  },
  "updated_on": 1775034399,
  "type": "purchase",
  "paymentMethod": "APPLEPAY",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "errorCode": "NA",
  "force_recurring": false,
  "created_on": 1775034399,
  "merchantRef": "69cce01f5bae56fd5547a993",
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "name": "e-commerce",
        "quantity": 1.0,
        "price": 10.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 10.0,
    "requestAmount": 10.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "taxAmount": 0.0,
    "taxPercent": 0.0,
    "request_client_details": [],
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
    "legal_name": "Omega Pixel",
    "brand_name": "Omega Pixel",
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
      "timestamp": 1775034399
    }
  ],
  "is_test": false,
  "brand_id": "f1764688-d991-481b-be63-9ee7f33dcd31",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS1032",
  "issued": "2026-04-01",
  "due": 1775034399,
  "refund_upto": 0,
  "cc_descriptor": "",
  "fraudScore": "NA",
  "trustScore": "NA",
  "extraFee": "0",
  "paidOn": 0,
  "receivedAmt": 0.0,
  "taxAmount": 0.0,
  "surcharge": 0.0,
  "surchargeType": "",
  "sessionId": "",
  "refund_availability": "NONE",
  "refundable_amount": 0.0,
  "success_redirect": "https://google.com/",
  "failure_redirect": "https://facebook.com/",
  "pending_redirect": "https://paysecure.net",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.com",
  "failure_callback": "https://your.failure.callback.com",
  "platform": "API",
  "created_from_ip": "103.80.161.238",
  "checkout_url": "https://api.choicepay.ca/payments/6b5a5977ac8e022facb31f3346f61ed0/",
  "direct_post_url": "https://api.choicepay.ca/api/v1/p/69cce01f5bae56fd5547a993/",
  "payoutProcess": false
}
```


# Get Status 3

This API tells you about all the details of a purchase (PayIn), including its history

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
async getStatus3(
  purchaseId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PurchaseSuccess4>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchaseSuccess4`](../../doc/models/purchase-success-4.md).

## Example Usage

```ts
const purchaseId = 'purchaseId2';

try {
  const response = await apIsApi.getStatus3(purchaseId);

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
  "purchaseId": "69cce01f5bae56fd5547a993",
  "client": {
    "customerId": "NA",
    "email": "himanshu1@paysecure.net",
    "full_name": "OpHM",
    "date_of_birth": "1800-01-01",
    "street_address": "SB-124",
    "country": "BR",
    "city": "DLJPR",
    "zip_code": "110001",
    "cc": [],
    "bcc": [],
    "stateCode": "DL"
  },
  "updated_on": 1775034399,
  "type": "purchase",
  "paymentMethod": "GOOGLEPAY",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "errorCode": "NA",
  "force_recurring": false,
  "created_on": 1775034399,
  "merchantRef": "69cce01f5bae56fd5547a993",
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "name": "e-commerce",
        "quantity": 1.0,
        "price": 10.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 10.0,
    "requestAmount": 10.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "taxAmount": 0.0,
    "taxPercent": 0.0,
    "request_client_details": [],
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
    "legal_name": "Omega Pixel",
    "brand_name": "Omega Pixel",
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
      "timestamp": 1775034399
    }
  ],
  "is_test": false,
  "brand_id": "f1764688-d991-481b-be63-9ee7f33dcd31",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS1032",
  "issued": "2026-04-01",
  "due": 1775034399,
  "refund_upto": 0,
  "cc_descriptor": "",
  "fraudScore": "NA",
  "trustScore": "NA",
  "extraFee": "0",
  "paidOn": 0,
  "receivedAmt": 0.0,
  "taxAmount": 0.0,
  "surcharge": 0.0,
  "surchargeType": "",
  "sessionId": "",
  "refund_availability": "NONE",
  "refundable_amount": 0.0,
  "success_redirect": "https://google.com/",
  "failure_redirect": "https://facebook.com/",
  "pending_redirect": "https://paysecure.net",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.com",
  "failure_callback": "https://your.failure.callback.com",
  "platform": "API",
  "created_from_ip": "103.80.161.238",
  "checkout_url": "https://api.choicepay.ca/payments/6b5a5977ac8e022facb31f3346f61ed0/",
  "direct_post_url": "https://api.choicepay.ca/api/v1/p/69cce01f5bae56fd5547a993/",
  "payoutProcess": false
}
```


# Purchase 1

To Initiate a payment, the very first call to make is `/purchases` with the required data in the request body.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.email | The customer's email. |
| client.city | The customer's city. |
| client.country | ISO-3166 Country Code. Must be upper case. Example “SG” (Alpha2) |
| client.stateCode | Example “AL”, “XZ”. Must be in upper case. |
| Client.street_address | The customer's address. |
| client.zip_code | The customer's ZIP or postal code. If country=US, zip format must be NNNNN or NNNNN-NNNN. |
| purchase.currency | ISO 4217 code for currency you want to send the transaction in.  <br>  <br>Please note, the currency has to be enabled by the account manager for your account. |
| purchase.products | An object which contains the list of products which the customer is buying. |
| purchase.products.name | The name of the product. |
| purchase.products.price | Price in decimal format.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
| brand_id | Obtain from Dashboard section of your merchant account login. |
| success_redirect | URL to send the user if the transactions is successful. |
| pending_redirect | URL to send the user if the transactions is in pending. |
| failure_redirect | URL to send the user if the transactions is unsuccessful. |

## Essential Optional Parameters

### merchantRef

The `merchantRef` parameter, although not mandatory, is strongly advised for merchants to specify. Its inclusion offers two significant advantages for the merchant:

1. **Prevention of Duplicate Requests:** When a `merchantRef` is utilized, it acts as a unique identifier. This means that if a second purchase request is made using the same `merchantRef` (reference number), the system will recognize it and prevent duplicate transactions from occurring. This prevents unintended or duplicate purchases.

2. **Facilitation of Transaction Retrieval:** In situations where the response from the initial purchase request times out or the 'purchaseId' isn't received, having the `merchantRef` allows the merchant to retrieve detailed transaction information. This ensures they can track and access the specific purchase details related to that reference, even if the immediate response was not received.

However, if the merchant does not specify the 'merchantRef' parameter, the platform will automatically assign and use an internal 'purchaseId' as a reference for that transaction.

Upon successul create on a Purchase you'd get a `"purchaseId"` . Use this ID for the next step in Server to server call by calling `p/{purchaseId}/?s2s=true .`

### paymentMethod

The `paymentMethod` parameter identifies which payment solution merchant wants to use to perform a transaction. If parameter is provided, than Paysecure will perform direct payment with the selected payment method instead of loading Paysecure URL.

### Errors

If there are any errors then it'll be in the format of :

```json
{
    "message": "descriptive error message",
    "code": "error_code"
}

```

### Possible Error Messages

| **Error Messages** |
| --- |
| Allowed Limit for this card for particular time period has been consumed |
| some Mandatory Parameter are missing |
| Invalid format of Date_of_Birth \[allowed format: yyyy-mm-dd\] |
| Invalid Email Format |
| Please submit Valid Alpha2 Country Code Ex:(AF,IN) in \\"country\\" parameter |
| Please pass Valid State Code |
| Please pass valid street address in \\"street_address\\" parameter |
| Please pass valid city name in \\"city\\" parameter |
| Please pass valid postal Code name in \\"zip_code\\" parameter |
| You are not Allowed for Live Transaction |
| Merchant Limit is not set |
| Minimum amount is not set for this merchant |
| Brand not found ! |
| Your charges setting is incomplete .Plese Contact to Administrator. |
| Only {{currencyCode}} currency is allowed. |
| Transaction amount must be equal or greater to minimum trans amount |
| Invalid_Parameter  <br>You'd usually get it when one or more mandatory parameters are not present in the request. |

:information_source: **Note** This endpoint does not require authentication.

```ts
async purchase1(
  body: PurchaseRequest2,
  requestOptions?: RequestOptions
): Promise<ApiResponse<OpenBankingEuUk>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchaseRequest2`](../../doc/models/purchase-request-2.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`OpenBankingEuUk`](../../doc/models/open-banking-eu-uk.md).

## Example Usage

```ts
const body: PurchaseRequest2 = {
  client: {
    email: 'alpha7.bravo@bravapay.com',
    country: 'GB',
    city: 'London',
    stateCode: 'LND',
    fullName: 'shiba sharma',
    streetAddress: '10 New Burlington StreetApt. 214',
    zipCode: 'SW1A0AA',
    phone: '+447755564318',
    gender: 'male',
    dateOfBirth: '2004-04-31',
  },
  purchase: {
    currency: 'GBP',
    products: [
      {
        name: 'e-commerce',
        price: '10',
      },
      {
        name: 'retail',
        price: '11',
      }
    ],
    total: 21,
  },
  paymentMethod: 'OPEN-BANKING',
  brandId: '{{Your.brandID}}',
  merchantRef: '<your_transactionId>',
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
};

try {
  const response = await apIsApi.purchase1(body);

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
  "purchaseId": "68c3a4a031ee334ef2c02b2a",
  "client": {
    "customerId": "NA",
    "email": "alpha7.bravo@bravapay.com",
    "date_of_birth": "2004-04-31",
    "street_address": "10 New Burlington StreetApt. 214",
    "country": "GB",
    "city": "London",
    "zip_code": "SW1A0AA",
    "full_name": "shiba sharma",
    "phone": "+447755564318",
    "gender": "male",
    "stateCode": "LND"
  },
  "updated_on": 1757652134,
  "type": "purchase",
  "paymentMethod": "OPEN-BANKING",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "errorCode": "NA",
  "redirectType": "POST",
  "force_recurring": false,
  "created_on": 1757652128,
  "merchantRef": "68c3a4a031ee334ef2c02b2a",
  "merchantName": "merchantName",
  "purchase": {
    "currency": "GBP",
    "products": [
      {
        "name": "e-commerce",
        "quantity": 1.0,
        "price": 10.0,
        "discount": 0,
        "tax_percent": "0.00"
      },
      {
        "name": "retail",
        "quantity": 1.0,
        "price": 11.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 21.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "taxAmount": 0.0,
    "taxPercent": 0.0,
    "request_client_details": [],
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 21.0,
    "currency": "INR",
    "net_amount": 21.0,
    "fee_amount": 0.0,
    "pending_amount": 0.0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1757652129,
    "remote_paid_on": 1757652129
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
    "legal_name": "Testing",
    "brand_name": "Testing",
    "registration_number": "",
    "tax_number": ""
  },
  "transaction_data": {
    "payment_method": "",
    "flow": "payform",
    "extra": {
      "amount": 100.0,
      "masked_pan": "OPEN-BANKING"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "183.83.55.235, 162.158.91.128, 18.68.47.183",
        "type": "execute",
        "payment_method": "OPEN-BANKING",
        "flow": "payform",
        "successful": true,
        "country": "OPEN-BANKING",
        "processing_time": 1757652129,
        "extra": {
          "amount": 100.0,
          "masked_pan": "OPEN-BANKING"
        }
      }
    ]
  },
  "status": "PAYMENT_IN_PROCESS",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1757652128
    },
    {
      "status": "pending_execute",
      "timestamp": 1757652129
    },
    {
      "status": "payment_in_process",
      "timestamp": 1757652134
    }
  ],
  "is_test": false,
  "brand_id": "59c5ed48-caf9-464a-ba54-26e1e02bc1bc",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS93",
  "issued": "2025-09-12",
  "due": 1757652128,
  "refund_upto": 0,
  "cc_descriptor": "",
  "fraudScore": "0",
  "trustScore": "0",
  "paidOn": 0,
  "taxAmount": 0.0,
  "surcharge": 0.0,
  "surchargeType": "",
  "sessionId": "",
  "refund_availability": "NONE",
  "refundable_amount": 0.0,
  "success_redirect": "https://your.success.redirect.com",
  "pending_redirect": "https://your.pending.redirect.com",
  "failure_redirect": "https://your.failure.redirect.com",
  "success_callback": "https://your.success.callback.com",
  "failure_callback": "https://your.failure.callback.com",
  "platform": "API",
  "created_from_ip": "183.83.55.235, 162.158.91.128, 18.68.47.183",
  "checkout_url": "https://api.choicepay.ca/payments/63cddfa1a4948aba8e8ee9f319e3428f/",
  "payoutProcess": false
}
```


# Get Status 11

This API tells you about all the details of a purchase, including its history

### Mandatory

you need to pass the `PurchaseID` in the API URL

### Possible Value of Status

| **Status** | **Notes** |
| --- | --- |
| created | When Purchase order is created. |
| paid | Transaction Successful |
| payment_in_process | Payment is under Processing |
| chargeback | Payment is chargeback state |
| refund_in_process | Refund is under Processing. |
| expired | Purchase has Expired. |
| overdue | Purchase is Overdued. |
| cancelled | Purchase is cancelled. |
| error | Transaction has Failed. |
| refunded | Payment is refunded |

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
async getStatus11(
  requestOptions?: RequestOptions
): Promise<ApiResponse<PurchasesSuccess>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchasesSuccess`](../../doc/models/purchases-success.md).

## Example Usage

```ts
try {
  const response = await apIsApi.getStatus11();

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
  "purchaseId": "64bfdb7df63e36669499e82f",
  "client": {
    "bank_account": "",
    "bank_code": "",
    "email": "example@paysecure.net",
    "phone": "",
    "full_name": "",
    "date_of_birth": "",
    "personal_code": "",
    "street_address": "test test",
    "country": "IN",
    "city": "123",
    "zip_code": "234567",
    "shipping_street_address": "",
    "shipping_country": "",
    "shipping_city": "",
    "shipping_zip_code": "",
    "cc": [],
    "bcc": [],
    "legal_name": "",
    "brand_name": "",
    "registration_number": "",
    "tax_number": "",
    "stateCode": "ca"
  },
  "updated_on": 1690296521,
  "type": "purchase",
  "force_recurring": false,
  "created_on": 1690295168,
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "name": "dk",
        "quantity": 1,
        "price": 9,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 9,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1,
    "request_client_details": [],
    "timezone": "America/Edmonton",
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 9,
    "currency": "USD",
    "net_amount": 9,
    "fee_amount": 10.2591,
    "pending_amount": 0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1690295205,
    "remote_paid_on": 1690295205
  },
  "issuer_details": {
    "website": "",
    "legal_street_address": "",
    "legal_country": "",
    "legal_city": "",
    "legal_zip_code": "",
    "bank_accounts": [
      {
        "bank_account": "",
        "bank_code": ""
      }
    ],
    "legal_name": "shoes",
    "brand_name": "shoes",
    "registration_number": "",
    "tax_number": ""
  },
  "transaction_data": {
    "payment_method": "",
    "flow": "payform",
    "extra": {
      "expiry_month": "10",
      "amount": 9,
      "card_issuer": "1-800-432-3117",
      "masked_pan": "411111XXXXXX1111",
      "card_brand": "VISA",
      "card_issuer_country": "US",
      "cardholder_name": "dk",
      "expiry_year": "23"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "149.86.53.48",
        "type": "execute",
        "payment_method": "VISA",
        "flow": "payform",
        "successful": true,
        "country": "US",
        "processing_time": 1690295205,
        "extra": {
          "expiry_month": "10",
          "amount": 9,
          "card_issuer": "1-800-432-3117",
          "masked_pan": "411111XXXXXX1111",
          "card_brand": "VISA",
          "card_issuer_country": "US",
          "cardholder_name": "dk",
          "expiry_year": "23"
        }
      }
    ]
  },
  "status": "PAID",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1690295168
    },
    {
      "status": "pending_execute",
      "timestamp": 1690295193
    },
    {
      "status": "payment_in_process",
      "timestamp": 1690295205
    },
    {
      "status": "paid",
      "timestamp": 1690296521
    },
    {
      "status": "viewed",
      "timestamp": 1690299929
    }
  ],
  "viewedOn": 1690299929,
  "is_test": false,
  "brand_id": "bd69e8a5-adcf-40de-9e43-2b87cb129a5e",
  "merchantRef": "d9db7ec0-f94c-4a9d-8883-54c19c222d81",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS192",
  "issued": "2023-07-25",
  "due": 1690295168,
  "refund_upto": 1705843623,
  "cc_descriptor": "test-cardeye",
  "refund_availability": "NONE",
  "refundable_amount": 9,
  "success_redirect": "https://google.com",
  "failure_redirect": "https://yahoo.com",
  "cancel_redirect": "",
  "success_callback": "",
  "platform": "API",
  "created_from_ip": "149.86.53.48",
  "checkout_url": "http://18.214.100.20/payments/64bfdb7df63e36669499e82f/",
  "direct_post_url": "http://18.214.100.20/api/v1/p/64bfdb7df63e36669499e82f/"
}
```


# Refund 1

This API is used to initate refund of the purchases that have status as `PAID` can be initiated for refund

Once the refund has been initiated, the status of the purchase would become `REFUND_IN_PROCESS` and once the refund has been approved by the bank, the status woud become `REFUNDED`

Purchase ID is **mandatory** for this API.

Currently we don't support partial refunds.

### Response Examples

In the response examples you can see instances of both `successful` and `unsuccessful` in refund of purchases.

:information_source: **Note** This endpoint does not require authentication.

```ts
async refund1(
  requestOptions?: RequestOptions
): Promise<ApiResponse<RefundSuccess1>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`RefundSuccess1`](../../doc/models/refund-success-1.md).

## Example Usage

```ts
try {
  const response = await apIsApi.refund1();

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
    if (error instanceof RefundError) {
      console.log(error.result);
    }
  }
}
```

## Example Response *(as JSON)*

```json
{
  "purchaseId": "64bfdb7df63e36669499e82f",
  "client": {
    "bank_account": "",
    "bank_code": "",
    "email": "example@paysecure.net",
    "phone": "",
    "full_name": "",
    "date_of_birth": "",
    "personal_code": "",
    "street_address": "test test",
    "country": "IN",
    "city": "123",
    "zip_code": "234567",
    "shipping_street_address": "",
    "shipping_country": "",
    "shipping_city": "",
    "shipping_zip_code": "",
    "cc": [],
    "bcc": [],
    "legal_name": "",
    "brand_name": "",
    "registration_number": "",
    "tax_number": "",
    "stateCode": "ca"
  },
  "updated_on": 1690302819,
  "type": "purchase",
  "force_recurring": false,
  "created_on": 1690295168,
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "name": "dk",
        "quantity": 1,
        "price": 9,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 9,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1,
    "request_client_details": [],
    "timezone": "America/Edmonton",
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 9,
    "currency": "USD",
    "net_amount": 9,
    "fee_amount": 10.2591,
    "pending_amount": 0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1690295205,
    "remote_paid_on": 1690295205
  },
  "issuer_details": {
    "website": "",
    "legal_street_address": "",
    "legal_country": "",
    "legal_city": "",
    "legal_zip_code": "",
    "bank_accounts": [
      {
        "bank_account": "",
        "bank_code": ""
      }
    ],
    "legal_name": "shoes",
    "brand_name": "shoes",
    "registration_number": "",
    "tax_number": ""
  },
  "transaction_data": {
    "payment_method": "",
    "flow": "payform",
    "extra": {
      "expiry_month": "10",
      "amount": 9,
      "card_issuer": "1-800-432-3117",
      "masked_pan": "411111XXXXXX1111",
      "card_brand": "VISA",
      "card_issuer_country": "US",
      "cardholder_name": "dk",
      "expiry_year": "23"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "149.86.53.48",
        "type": "execute",
        "payment_method": "VISA",
        "flow": "payform",
        "successful": true,
        "country": "US",
        "processing_time": 1690295205,
        "extra": {
          "expiry_month": "10",
          "amount": 9,
          "card_issuer": "1-800-432-3117",
          "masked_pan": "411111XXXXXX1111",
          "card_brand": "VISA",
          "card_issuer_country": "US",
          "cardholder_name": "dk",
          "expiry_year": "23"
        }
      },
      {
        "client_ip": "149.86.53.48",
        "type": "refund",
        "successful": true,
        "processing_time": 1690302819,
        "extra": {
          "amount": 9
        }
      }
    ]
  },
  "status": "REFUNDED",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1765294731
    },
    {
      "status": "pending_execute",
      "timestamp": 1765294744
    },
    {
      "status": "payment_in_process",
      "timestamp": 1765294754
    },
    {
      "status": "paid",
      "timestamp": 1765297331
    },
    {
      "status": "refunded",
      "timestamp": 1765624009
    }
  ],
  "viewedOn": 1690299929,
  "is_test": false,
  "brand_id": "bd69e8a5-adcf-40de-9e43-2b87cb129a5e",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS192",
  "issued": "2023-07-25",
  "due": 1690295168,
  "refund_upto": 1705843623,
  "cc_descriptor": "test-cardeye",
  "refund_availability": "NONE",
  "refundable_amount": 0,
  "success_redirect": "https://google.com",
  "failure_redirect": "https://yahoo.com",
  "cancel_redirect": "",
  "success_callback": "",
  "platform": "API",
  "created_from_ip": "149.86.53.48",
  "checkout_url": "http://18.214.100.20/payments/64bfdb7df63e36669499e82f/",
  "direct_post_url": "http://18.214.100.20/api/v1/p/64bfdb7df63e36669499e82f/"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`RefundError`](../../doc/models/refund-error.md) |


# Create Customer

**OVERIEW**

The **createCustomer API** allows merchants to create a customer profile on Paysecure when a user visits their website, facilitating a seamless payment experience by pre-filling the customer's details, on the Paysecure Cashier.

The API takes in customer information and returns a unique customerID that can be passed in purchase payload, eliminating the need for customers to manually enter their details during transactions.

| Parameter | Type | **Required** | Description | Example |
| --- | --- | --- | --- | --- |
| merchantCustomerId | String | Yes | unique customer ID provided by merchant. This can be email, mobile or an alphanumeric string | [rahultestcustomer@paysecure.net](https://mailto:rahultestcustomer@paysecure.net) |
| fullName | String | Yes | Full name of the customer. | Rahul Agarwal |
| emailId | String | Yes | Email address of the customer. | [test@paysecure.net](https://mailto:test@paysecure.net) |
| dateOfBirth | String | Optional | Customer's date of birth in YYYY-MM-DD format. | 1995-12-27 |
| phoneNo | String | Yes | Customer's phone number. Preferred with the country code | +91 797639082 |
| city | String | Optional | City of the customer. | Jaipur |
| stateCode | String | Yes | State code of the customer. | RJ |
| zipCode | String | Optional | Postal code of the customer's location. | 302018 |
| address | String | Optional | Full address of the customer. | House Number 53, Vaishali Nagar, Jaipur |
| country | String | Yes | Country code (ISO 3166-1 alpha-2). | IN |
| custRegDate | Sting | Optional | Customer registration date on merchant site in YYYY-MM-DD format. | 2023-12-27 |
| successTxn | String | Optional | Number of successful transactions customer has carried on merchant site. | 32 |

### **User Flow**

1. **Customer visits merchant's website**: The customer selects the product or service and proceeds to checkout page.

2. **Merchant calls the** **`createCustomer`** **API**: The merchant sends a `POST` request to the Paysecure API with the customer's details.

3. **Customer ID generation**: Paysecure processes the request and generates a unique `customerId` which is returned in the response.

4. **Payment Process**: The merchant uses the `customerId` for subsequent session creation, ensuring the customer doesn’t need to re-enter their details for future payments.

---


### **Benefits**

- **Seamless user experience**: The customer does not have to enter their details manually for every purchase.

- **Faster Checkout**: The merchant can use the `customerId` for faster payment processing.

- **Data Security**: Customer details are stored securely and can be reused across transactions, reducing the chances of errors.

### Implementing createCustomer on merchant site:

The `createCustomer` can be implemented on merchant site in one of two ways, depending on merchant’s integration flow:

**At Checkout:**

When a customer initiates the checkout process, your system should invoke the `createCustomer` API, before actually starting the session.

- **Call** **`createCustomer`**: This API call generates a unique customer ID.

- **Use of Customer ID:** Pass the returned customer ID in Session API, when creating a payment session.

**Upon Customer Login:**

Alternatively, merchants may choose to call `createCustomer` at the time of customer login on their site.

- **Persistent Customer Profiles:** This approach can help build or maintain a persistent customer profile, ensuring the customer ID is available for any subsequent payment sessions without needing to call `createCustomer` again.

- **Integration Flexibility:** This is useful for merchants who want to initialize customer data early in the customer journey rather than during checkout.

The method you choose depends on your business requirements and how your system is architected. Regardless of when you call it, the resulting customer ID must be passed to the `createSession` API to initiate a payment session.

:information_source: **Note** This endpoint does not require authentication.

```ts
async createCustomer(
  brandId: string,
  body: CreateCustomerRequest1,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success19>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `brandId` | `string` | Header, Required | - |
| `body` | [`CreateCustomerRequest1`](../../doc/models/create-customer-request-1.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success19`](../../doc/models/success-19.md).

## Example Usage

```ts
const brandId = 'brand_id_value';

const body: CreateCustomerRequest1 = {
  fullName: 'Rahul Agarwal',
  emailId: 'rahul+26@paysecure.net',
  dateOfBirth: '1994-06-03',
  phoneNo: '+91 797639082',
  city: 'Jaipur',
  stateCode: 'RJ',
  zipCode: '302018',
  address: 'House Number 53, Vaishali Nagar, Jaipur',
  country: 'IN',
  merchantCustomerId: 'rahultestcustomer@paysecure.net',
  custRegDate: '2023-12-27',
  successTxn: '32',
  extraParam: {
    param1: 'value1',
    param2: 'value2',
    param3: 'value3',
    param4: 'value4',
  },
};

try {
  const response = await apIsApi.createCustomer(
    brandId,
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
  "customerId": "691afbc6fd96d34a8113a34d",
  "merchantCustomerId": "rahultestcustomer@paysecure.net",
  "fullName": "Rahul Agarwal",
  "emailId": "rahul+26@paysecure.net",
  "dateOfBirth": "1994-06-03",
  "phoneNo": "+91 797639082",
  "brandID": "1d666074-39be-4b90-aec9-e9de78fbdcb9",
  "city": "Jaipur",
  "zipCode": "302018",
  "address": "House Number 53, Vaishali Nagar, Jaipur",
  "country": "IN",
  "stateCode": "RJ",
  "custRegDate": "2023-12-27",
  "successTrans": 0,
  "createdOn": 1763376070,
  "lastUpdated": 0,
  "lastActivity": 1763376070,
  "extraParam": {
    "param1": "value1",
    "param2": "value2",
    "param3": "value3",
    "param4": "value4"
  }
}
```


# Get Customer

This endpoint makes an HTTP GET request to retrieve customer information from the Paysecure API.

### Request

The request does not include any query parameters, but it uses a raw request body with the following parameter "merchantCustomerId", which will be the customer id on the merchant's side.

### Response

The response of this request can be documented as a JSON schema.

:information_source: **Note** This endpoint does not require authentication.

```ts
async getCustomer(
  brandId: string,
  accept: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success19>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `brandId` | `string` | Header, Required | - |
| `accept` | `string` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success19`](../../doc/models/success-19.md).

## Example Usage

```ts
const brandId = 'brand_id_value';

const accept = '*/*';

try {
  const response = await apIsApi.getCustomer(
    brandId,
    accept
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
  "customerId": "691afbc6fd96d34a8113a34d",
  "merchantCustomerId": "rahultestcustomer1@paysecure.net",
  "fullName": "Rahul Agarwal",
  "emailId": "rahul+26@paysecure.net",
  "dateOfBirth": "1994-06-03",
  "phoneNo": "+91 797639082",
  "brandID": "1d666074-39be-4b90-aec9-e9de78fbdcb9",
  "city": "Jaipur",
  "zipCode": "302018",
  "address": "House Number 53, Vaishali Nagar, Jaipur",
  "country": "IN",
  "stateCode": "RJ",
  "custRegDate": "2023-12-27",
  "successTrans": 0,
  "createdOn": 1763376070,
  "lastUpdated": 0,
  "lastActivity": 1763376070,
  "extraParam": {
    "param1": "value1",
    "param2": "value2",
    "param3": "value3",
    "param4": "value4"
  }
}
```


# Create Session CIT

**OVERIEW**

The `createSession` API is designed to initiate a payment session for a customer after their profile has been created via the **createCustomer** API. The session is automatically generated at the backend on the merchant’s checkout URL. This session allows the customer to continue with their transaction without having to manually interact with the session URL, and ensures the session remains active until the payment is completed or the session expires.

This API improves the user experience by reducing transaction failures and enhancing the overall payment process, thus reducing transaction churn rates.

### Mandatory Parameters

| Parameter | Type | Description | Example |
| --- | --- | --- | --- |
| customerId | String | The unique ID of the customer (generated from createCustomer). | 6731a609b6bb5a43ad66c4a6 |

To register a mandate, pass mandate related parameters in the Create Session API to create a mandate registration purchase. Post transaction completion, use Get Status API and Webhooks to capture mandate registration details.

### Additional **parameters for this usecase:**

| **Parameter** | **Notes** |
| --- | --- |
| payment_type | Mandatory.  <br>To be passed as "mandate". |
| mandate | Mandatory.  <br>This object is mandatory for mandate flow |
| mandate.mandate_max_amount | Optional  <br>Maximum amount for a mandate. |
| mandate.amount_variability | Optional  <br>Specifies whether the amount is fixed or variable for each recurrence.  <br>  <br>Possible values: Fixed or Variable |
| mandate.start_date | Mandatory  <br>Specifies the time when the mandate will start. |
| mandate.end_date | Mandatory  <br>Specifies the time when the mandate will end. |
| mandate.frequency | Mandatory  <br>Defines the frequency of mandate execution, how often a customer should be charged.  <br>  <br>Possible Values:  <br>**ONETIME**: This is for a one-time mandate. The customer provides authorisation to debit their account a single time for a specific amount.  <br>  <br>**DAILY**: Recurring mandate. The customer provides authorisation to debit their account daily for a specific amount.  <br>  <br>**WEEKLY**: Recurring mandate. Authorisation given by a customer to debit their account weekly once for a specified amount.  <br>  <br>**FORTNIGHTLY**: Recurring mandate. The customer provides authorisation to debit their account fortnightly for a specific amount.  <br>  <br>**MONTHLY**: Recurring mandate. The customer provides authorisation to debit their account monthly for a specific amount.  <br>  <br>**BIMONTHLY**: Recurring mandate. The customer provides authorisation to debit their account bimonthly for a specific amount.  <br>  <br>**QUARTERLY**: Recurring mandate. The customer provides authorisation to debit their account quarterly for a specific amount.  <br>  <br>**HALFYEARLY**: Recurring mandate. The customer provides authorisation to debit their account once in every 6 months for a specific amount.  <br>  <br>**YEARLY**: Recurring mandate. The customer provides authorisation to debit their account once a year for a specific amount.  <br>  <br>**ASPRESENTED**: For cases where the scheduling is handled by the merchant. The customer provides authorization to debit their account whenever there is an execution request. |
| mandate.rule | Optional.  <br>Indicates the recurrence rule of the mandate. This rule is not required for onetime, daily, and aspresented recurrence patterns.  <br>Possible values: on/before/after  <br>By Default: on |
| mandate.value | Conditional.  <br>The recurrence Value of the mandate.  <br>It is not required for ONETIME, DAILY and ASPRESENTED frequencies.  <br>  <br>Possible values:  <br>For WEEKLY: The value should be 1-Monday to 7-Sunday.  <br>For MONTHLY, BIMONTHLY, QUARTERLY, HALFYEARLY or YEARLY: The value should be between 1 to 30/31 days.  <br>  <br>By Default: The value will be treated as 1. |

### **Usage Flow**

1. **Customer completes the** **`createCustomer`** **API**: Once the customer is created via the `createCustomer` API, the merchant proceeds to call the `createSession` API to generate a session.

2. **Merchant sends** **`createSession`** **request**: The merchant sends a `POST` request to the `createSession` API with the customer’s `customerId` and the merchant’s `brandId`.

3. **Session created automatically on the checkout URL**: PaySecure creates the session and associates it with the merchant’s checkout page. This session remains active on the backend, allowing the customer to continue the payment process without interruption.

4. **Customer proceeds to checkout**: The customer is redirected to the checkout page as part of the merchant's payment flow, where the session is automatically validated. The session remains active for a set period, allowing the customer to complete the payment without needing to manually interact with the session URL.

5. **Session Expiry**: The session expires after the set expiration time (`expiryOn`), ensuring the payment process is completed within the defined window. Default is 15 mins from the creation time.

---


### **Benefits**

- **Seamless Checkout**: The session URL is automatically generated and active at the backend, ensuring a smoother and uninterrupted customer experience.

- **Reduced Transaction Failures**: By ensuring the session remains active during the payment process, the chances of transaction failures due to session timeouts are minimized.

- **Improved User Experience**: The customer does not need to click on a session URL or navigate away from the page, leading to faster and more secure payment processing.

:information_source: **Note** This endpoint does not require authentication.

```ts
async createSessionCit(
  brandId: string,
  body: CreateSessionCitRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success32>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `brandId` | `string` | Header, Required | - |
| `body` | [`CreateSessionCitRequest`](../../doc/models/create-session-cit-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success32`](../../doc/models/success-32.md).

## Example Usage

```ts
const brandId = 'brand_id_value';

const body: CreateSessionCitRequest = {
  customerId: '685f870cf3435a2d5b35ee08',
  currency: 'EUR',
  products: [
    {
      name: 'Product1',
      price: '10',
    },
    {
      name: 'Product2',
      price: '10',
    }
  ],
  totalAmount: '21',
  paymentMethod: 'VISA',
  successRedirect: 'https://merchant.com/success',
  pendingRedirect: 'https://merchant.com/pending',
  failureRedirect: 'https://merchant.com/failure',
  successCallback: 'https://merchant.com/webhook/success',
  failureCallback: 'https://merchant.com/webhook/failure',
  paymentType: 'mandate',
  mandate: {
    mandateMaxAmount: '5000',
    amountVariability: 'Fixed',
    startDate: '1598965200',
    endDate: '1914141600',
    frequency: 'MONTHLY',
    rule: 'on',
    value: 1,
  },
};

try {
  const response = await apIsApi.createSessionCit(
    brandId,
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
  "sessionUrl": "https://api.paysecure.net/api/v1/session/685bdefb9a1a8f16b3c4489c/",
  "brandId": "<UUID>",
  "customerId": "685bdd529a1a8f16b3c445a4",
  "sessionId": "685cc8515e3af922dd0e8c31",
  "expiryOn": 1750852223,
  "createdOn": 1750851323,
  "expiry_in_mins": "86400"
}
```


# Create Purchase CIT

**OVERIEW**

The `create Purchase` API is designed to initiate a payment for a merchant who doesn't want to use Paysecure's cashier and wants to keep everything S2S.

The merchant doesn't need to create a customer in this case and directly needs to call the purchase API and then call the S2S API after that.

### Additional **parameters for this usecase:**

| **Parameter** | **Notes** |
| --- | --- |
| payment_type | Mandatory.  <br>To be passed as "mandate". |
| paymentMethod | Mandatory.  <br>Example: MASTER, VISA |
| brand_id | Mandatory.  <br>Your brand id. |
| mandate | Mandatory.  <br>This object is mandatory for mandate flow |
| mandate.mandate_max_amount | Conditional.  <br>Mandatory when amount_variability is "Variable".  <br>Maximum amount for a mandate. |
| mandate.amount_variability | Optional  <br>Specifies whether the amount is fixed or variable for each recurrence.  <br>  <br>Possible values: Fixed or Variable |
| mandate.start_date | Optional  <br>Specifies the time when the mandate will start. |
| mandate.end_date | Optional  <br>Specifies the time when the mandate will end.  <br>(If not passed then indefinite) |
| mandate.frequency | Mandatory  <br>Defines the frequency of mandate execution, how often a customer should be charged.  <br>  <br>Possible Values:  <br>**ONETIME**: This is for a one-time mandate. The customer provides authorisation to debit their account a single time for a specific amount.  <br>  <br>**DAILY**: Recurring mandate. The customer provides authorisation to debit their account daily for a specific amount.  <br>  <br>**WEEKLY**: Recurring mandate. Authorisation given by a customer to debit their account weekly once for a specified amount.  <br>  <br>**FORTNIGHTLY**: Recurring mandate. The customer provides authorisation to debit their account fortnightly for a specific amount.  <br>  <br>**MONTHLY**: Recurring mandate. The customer provides authorisation to debit their account monthly for a specific amount.  <br>  <br>**BIMONTHLY**: Recurring mandate. The customer provides authorisation to debit their account bimonthly for a specific amount.  <br>  <br>**QUARTERLY**: Recurring mandate. The customer provides authorisation to debit their account quarterly for a specific amount.  <br>  <br>**HALFYEARLY**: Recurring mandate. The customer provides authorisation to debit their account once in every 6 months for a specific amount.  <br>  <br>**YEARLY**: Recurring mandate. The customer provides authorisation to debit their account once a year for a specific amount.  <br>  <br>**ASPRESENTED**: For cases where the scheduling is handled by the merchant. The customer provides authorization to debit their account whenever there is an execution request. |
| mandate.rule | Optional.  <br>Indicates the recurrence rule of the mandate. This rule is not required for onetime, daily, and aspresented recurrence patterns.  <br>Possible values: on/before/after  <br>By Default: on |
| mandate.value | Conditional.  <br>The recurrence Value of the mandate.  <br>It is not required for ONETIME, DAILY and ASPRESENTED frequencies.  <br>  <br>Possible values:  <br>For WEEKLY: The value should be 1-Monday to 7-Sunday.  <br>For MONTHLY, BIMONTHLY, QUARTERLY, HALFYEARLY or YEARLY: The value should be between 1 to 30/31 days.  <br>  <br>By Default: The value will be treated as 1. |

:information_source: **Note** This endpoint does not require authentication.

```ts
async createPurchaseCit(
  body: CreatePurchaseCitRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreatePurchaseCitRequest`](../../doc/models/create-purchase-cit-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const body: CreatePurchaseCitRequest = {
  client: {
    email: 'rahul@gmail.com',
    streetAddress: 'Flat 61 Priory Court Romford RM7 0FY',
    city: 'London',
    fullName: 'Rahul Agarwal',
    zipCode: '234567',
    country: 'GB',
    stateCode: 'LO',
    phone: '+44 07932665877',
  },
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'product name',
        price: '1',
      }
    ],
  },
  merchantRef: 'your-merchant-ref',
  paymentMethod: 'MASTER',
  brandId: 'your-brand-id',
  paymentType: 'mandate',
  mandate: {
    mandateMaxAmount: '5000',
    amountVariability: 'Fixed',
    startDate: '1598965200',
    endDate: '1914141600',
    frequency: 'MONTHLY',
    rule: 'on',
    value: 1,
  },
  successRedirect: 'https://merchant.com/success',
  pendingRedirect: 'https://merchant.com/pending',
  failureRedirect: 'https://merchant.com/failure',
  successCallback: 'https://merchant.com/webhook/success',
  failureCallback: 'https://merchant.com/webhook/failure',
};

try {
  const response = await apIsApi.createPurchaseCit(body);

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
    if (error instanceof Success33Error) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | [`Success33Error`](../../doc/models/success-33-error.md) |


# S2 S API

This API would be the 2nd in sequence to call if the call to `/purchases/` was successful in step 1. and you want to do the transaction via Server-to-Server mode.

The request body would contain the details of the card that's to be transacted upon.

### **Mandatory parameters in request body:**

| Parameter | **Notes** |
| --- | --- |
| remote_ip | IP address of the customer’s device used for transaction. Helps in fraud checks and risk scoring. Ex- 157.38.242.7 |
| user_agent | Full browser and operating system details captured from HTTP header. EX- Chrome/5.0 (X11; Linux x86_64) |
| accept_header | Browser’s accepted content types (from HTTP header). Used for validating request origin and device info. EX- text/html |

### **Essential parameters in request body:**

| Parameter | **Notes** |
| --- | --- |
| cardholder_name | Name of the cardholder |
| card_number | The card numbers Must be 10-20 characters. |
| expires | must be greater than the current month/year. |
| cvc | 3 or 4 digit |

**  
Other optional parameters in request body:**

| Parameter | **Notes** |
| --- | --- |
| language | Preferred language of the user’s browser . EX - en-US |
| java_enabled | Indicates if Java is enabled in the browser. Helps PSPs in device profiling. Ex- true/false |
| javascript_enabled | Indicates if JavaScript is enabled in the client browser. Used for 3DS or risk-based checks. Ex- true |
| color_depth | Bit depth of the display screen. Ex- 24 |
| utc_offset | Difference in minutes between local time and UTC. Used for location and timezone checks. Ex- 330 |
| screen_width | Width of the device screen in pixels. Used in device profiling. Ex- 1920 |
| screen_height | Height of the device screen in pixels. Ex- 1080 |

**Successful Response**

If all the details are correct you'll get a 202 response with staus as Pending

```json
{
    "status": "pending",
    "callback_url": "https://paysecure.net/payment/63bd0bf80fb42a076e8a4dd1/",
    "method": "GET"
}

```

If the response code is 202, after receiving the response body, direct the customer to the callback_url provided in the response.

**Errors**

If there are any errors then it'll be in the format of :

```json
{
    "message": "descriptive error message",
    "code": "error_code"
}

```

Please see the Status Code section for further details.

| **Error Messages** |
| --- |
| Client Ip could not be matched with Merchant Ip |
| Invalid Card Information |
| Card is Blocked |
| Different Type of key used to create purchase and payment |
| You charges setting is incomplete .Plese Contact to adminstrartor. |
| Allowed Attempt for this Transaction has been consumed |
| Invalid Card Expiry(Valid Format:MM/YY) must be greator than current month/year |
| Customer profile is Blocked |
| Customer/Card not allowed for transaction |

:information_source: **Note** This endpoint does not require authentication.

```ts
async s2SApi(
  s2S: boolean,
  body: S2SApiRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success1>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `s2S` | `boolean` | Query, Required | - |
| `body` | [`S2SApiRequest`](../../doc/models/s2-s-api-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success1`](../../doc/models/success-1.md).

## Example Usage

```ts
const s2S = true;

const body: S2SApiRequest = {
  cardholderName: 'dk',
  cardNumber: '4111111111111111',
  expires: '10/23',
  cvc: '345',
  rememberCard: 'on',
  remoteIp: '157.38.242.7',
  userAgent: 'Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/51.0.2704.103 Safari/537.36',
  acceptHeader: 'text/html',
  language: 'en-US',
  javaEnabled: false,
  javascriptEnabled: true,
  colorDepth: 24,
  utcOffset: 0,
  screenWidth: 1920,
  screenHeight: 1080,
};

try {
  const response = await apIsApi.s2SApi(
    s2S,
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
  "status": "pending",
  "callback_url": "http://18.214.100.20/api/v1/payment/64b034ecc6dccf7d329d9eb3/",
  "method": "GET"
}
```


# Get Mandate

This endpoint will be used to get all the details of a particular mandate. You can search for a particular mandate id or for a particular session id.

### Response **parameters:**

1. **totalDeductedAmount**  
   This is the total amount which is deducted from the user's account.

2. **recurringMandateIds**  
   This object returns a list of all the MIT transactions done for the respective mandate.

3. **nextMandateDate**  
   This is the date when the next recurring payment will happen.

:information_source: **Note** This endpoint does not require authentication.

```ts
async getMandate(
  accept: string,
  brandId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accept` | `string` | Header, Required | - |
| `brandId` | `string` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const accept = 'application/json';

const brandId = 'your-brand-value';

try {
  const response = await apIsApi.getMandate(
    accept,
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
    if (error instanceof Success36Error) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | Internal Server Error | [`Success36Error`](../../doc/models/success-36-error.md) |


# Create Purchase MIT

After the successful Mandate registration, Merchant will receive a mandate_id from Paysecure that should be stored against a customer at their end.

If the **merchant handles their own scheduling,** then for the subsequent transactions, the merchant is supposed to pass a combination of customer_id and mandate_id to do a debit. This API will perform a transaction with a PSP based on the mandate_id passed in the request.

If **Paysecure handles the scheduling for the merchant** on their behalf, then this API is not for them. The MIT transactions will be handled by Paysecure from our side.

Note:  
Recurring payments should only be done if the mandate registration has been successful and the mandate is ACTIVE.

:information_source: **Note** This endpoint does not require authentication.

```ts
async createPurchaseMit(
  accept: string,
  body: CreatePurchaseMitRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success38>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accept` | `string` | Header, Required | - |
| `body` | [`CreatePurchaseMitRequest`](../../doc/models/create-purchase-mit-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success38`](../../doc/models/success-38.md).

## Example Usage

```ts
const accept = '*/*';

const body: CreatePurchaseMitRequest = {
  client: {
    customerId: '685f870cf3435a2d5b35ee08',
    email: 'abby.aadeniran@gmail.com',
    phone: '+44 07932665877',
    fullName: 'Navya Jain',
    streetAddress: 'Flat 61 Priory Court Romford RM7 0FY',
    country: 'GB',
    city: 'London',
    zipCode: '234567',
    stateCode: 'LO',
  },
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'test',
        price: 1,
      }
    ],
  },
  merchantRef: '{{your-merchant-ref}}',
  brandId: '{{merchant_brand_id}}',
  paymentType: 'recurring',
  mandateId: '{{mandate-id}}',
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
};

try {
  const response = await apIsApi.createPurchaseMit(
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

## Example Response *(as JSON)*

```json
{
  "purchaseId": "69f8d407ea26ad15715ebb85",
  "client": {
    "customerId": "NA",
    "email": "recurring@yopmail.com",
    "date_of_birth": "1800-01-01",
    "street_address": "120, jaipur",
    "country": "CA",
    "city": "London",
    "zip_code": "W1S 3BE",
    "cc": [],
    "bcc": [],
    "stateCode": "QLD"
  },
  "updated_on": 1777914890,
  "type": "purchase",
  "paymentMethod": "VISA",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "errorCode": "NA",
  "force_recurring": false,
  "created_on": 1777914887,
  "merchantRef": "69f8d407ea26ad15715ebb85",
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "name": "gaming cards",
        "quantity": 1.0,
        "price": 1.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 1.0,
    "requestAmount": 1.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "taxAmount": 0.0,
    "taxPercent": 0.0,
    "request_client_details": [],
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 1.0,
    "currency": "USD",
    "net_amount": 1.0,
    "fee_amount": 0.0,
    "pending_amount": 0.0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1777914887,
    "remote_paid_on": 1777914887
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
    "legal_name": "Testing",
    "brand_name": "Testing",
    "registration_number": "",
    "tax_number": ""
  },
  "transaction_data": {
    "payment_method": "",
    "flow": "payform",
    "extra": {
      "expiry_month": "04",
      "amount": 1.0,
      "card_issuer": "REVOLUT BANK UAB",
      "masked_pan": "41659827****0724",
      "card_brand": "VISA",
      "card_issuer_country": "CH",
      "card_type": "DEBIT",
      "cardholder_name": "Amit Hooja",
      "expiry_year": "31"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "183.82.186.156",
        "type": "execute",
        "payment_method": "VISA",
        "flow": "payform",
        "successful": true,
        "country": "CH",
        "processing_time": 1777914887,
        "extra": {
          "expiry_month": "04",
          "amount": 1.0,
          "card_issuer": "REVOLUT BANK UAB",
          "masked_pan": "41659827****0724",
          "card_brand": "VISA",
          "card_issuer_country": "CH",
          "card_type": "DEBIT",
          "cardholder_name": "Amit Hooja",
          "expiry_year": "31"
        }
      }
    ]
  },
  "status": "PAID",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1777914887
    },
    {
      "status": "pending_execute",
      "timestamp": 1777914887
    },
    {
      "status": "paid",
      "timestamp": 1777914890
    }
  ],
  "is_test": false,
  "brand_id": "brand_id",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS1738",
  "issued": "2026-05-04",
  "due": 1777914887,
  "refund_upto": 1780503290,
  "cc_descriptor": "multitasklist",
  "fraudScore": "0",
  "trustScore": "0",
  "extraFee": "0",
  "totalRefunded": 0.0,
  "paidOn": 1777914890,
  "receivedAmt": 0.0,
  "taxAmount": 0.0,
  "surcharge": 0.0,
  "surchargeType": "",
  "sessionId": "",
  "refund_availability": "NONE",
  "refundable_amount": 1.0,
  "success_redirect": "https://staging.paysecure.net/getResponse.jsp?issucces=true",
  "failure_redirect": "https://staging.paysecure.net/getResponse.jsp?issucces=false",
  "cancel_redirect": "",
  "success_callback": "",
  "failure_callback": "https://staging.paysecure.net/merchant",
  "platform": "API",
  "created_from_ip": "2406:b400:75:22bd:b48e:a33e:4e26:a542",
  "checkout_url": "https://api.choicepay.ca/payments/0bc9c18600980b03a08fb030726428f8/",
  "direct_post_url": "https://api.choicepay.ca/api/v1/p/69f8d407ea26ad15715ebb85/",
  "payoutProcess": false,
  "payment_type": "recurring",
  "mandate_id": "69f8cfa1db7ca561ab23fed2"
}
```


# Revoke Mandate

Required for cases where the Paysecure is handling the scheduling of recurring payments. Use this API to revoke/cancel an ACTIVE mandate.

Note:  
Revoking a mandate should be done at the same instance this API is called. The mandate status should be updated to “REVOKED” at the same instant.

:information_source: **Note** This endpoint does not require authentication.

```ts
async revokeMandate(
  accept: string,
  brandid: string,
  body: RevokeMandateRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success39>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accept` | `string` | Header, Required | - |
| `brandid` | `string` | Header, Required | - |
| `body` | [`RevokeMandateRequest`](../../doc/models/revoke-mandate-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success39`](../../doc/models/success-39.md).

## Example Usage

```ts
const accept = 'application/json';

const brandid = 'your-brand-id';

const body: RevokeMandateRequest = {
  mandateId: '685cc8515e3af922dd0e8c31',
  command: 'revoke',
};

try {
  const response = await apIsApi.revokeMandate(
    accept,
    brandid,
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
  "mandateId": "6943aabe3f5c35b0f7849768",
  "message": "Mandate revoked successfully",
  "revokeDate": 1769857766,
  "status": "REVOKED"
}
```


# Pause Mandate

Required for cases where the Paysecure is handling the scheduling of recurring payments. Use this API to pause an ACTIVE mandate.

### Additional **parameters for this usecase:**

| **Parameter** | **Notes** |
| --- | --- |
| command | Mandatory.  <br>To be passed as "pause". |
| mandate_id | Mandatory. |
| pause_start_date | Optional  <br>Date in UNIX EPOCH timestamp (UTC timezone) format, when the mandate will be paused.  <br>If not passed, Default value will be the current date. |
| pause_end_date | Mandatory  <br>Date in UNIX EPOCH timestamp (UTC timezone) format, when the mandate status will be automatically changed to ACTIVE. |

Note:  
For pausing a mandate you need to keep the exact timestamp in mind.  
If a recurring payment is scheduled between the pause_start_date and pause_end_date then it will not be executed.

:information_source: **Note** This endpoint does not require authentication.

```ts
async pauseMandate(
  accept: string,
  brandId: string,
  body: PauseMandateRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PauseMandate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accept` | `string` | Header, Required | - |
| `brandId` | `string` | Header, Required | - |
| `body` | [`PauseMandateRequest`](../../doc/models/pause-mandate-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PauseMandate`](../../doc/models/pause-mandate.md).

## Example Usage

```ts
const accept = 'application/json';

const brandId = 'your-brand-id';

const body: PauseMandateRequest = {
  mandateId: '685cc8515e3af922dd0e8c31',
  command: 'pause',
  pauseStartDate: '1761985415',
  pauseEndDate: '1761985415',
};

try {
  const response = await apIsApi.pauseMandate(
    accept,
    brandId,
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
  "mandateId": "693c053feef6a6b6928b48b0",
  "pauseEndDate": 1769859769,
  "message": "Mandate paused configuration done successfully for the selected duration",
  "pauseStartDate": 1769857969,
  "status": "PAUSED"
}
```


# List Mandates

This endpoint will be used to list all the mandates for a particular customer of a merchant.

### Response **parameters:**

1. **totalDeductedAmount**  
   This is the total amount which is deducted from the user's account.

2. **recurringMandateIds**  
   This object returns a list of all the MIT transactions done for the respective mandate.

3. **nextMandateDate**  
   This is the date when the next recurring payment will happen.

:information_source: **Note** This endpoint does not require authentication.

```ts
async listMandates(
  customerId: string,
  email: string,
  accept: string,
  brandId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success40>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Query, Required | - |
| `email` | `string` | Query, Required | - |
| `accept` | `string` | Header, Required | - |
| `brandId` | `string` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success40`](../../doc/models/success-40.md).

## Example Usage

```ts
const customerId = '696bd627b0c24568ade4675e';

const email = 'test@gmail.com';

const accept = 'application/json';

const brandId = 'your-brand-id';

try {
  const response = await apIsApi.listMandates(
    customerId,
    email,
    accept,
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
  }
}
```

## Example Response *(as JSON)*

```json
{
  "mandates": [
    {
      "status": "ACTIVE",
      "frequency": "WEEKLY",
      "rule": "after",
      "value": 4,
      "totalDeductedAmount": "10.00",
      "recurringMandateIds": [
        "6973ad04fa54ee2cf14f438c",
        "697ce750e6446c7babfe4727"
      ],
      "email": "test@gmail.com",
      "nextMandateDate": 1770398106,
      "customer_id": "696bd627b0c24568ade4675e",
      "mandate_id": "696bc39a7bc779fac5201357",
      "mandate_max_amount": 120,
      "amount_variability": "Variable",
      "start_date": "1768670106"
    },
    {
      "status": "CREATED",
      "frequency": "WEEKLY",
      "rule": "on",
      "value": 6,
      "totalDeductedAmount": "0",
      "email": "test@gmail.com",
      "customer_id": "696bd627b0c24568ade4675e",
      "mandate_id": "696bd627b0c24568ade4675e",
      "mandate_max_amount": 120,
      "amount_variability": "Variable",
      "start_date": "1768674855",
      "session_id": ""
    },
    {
      "status": "ACTIVE",
      "frequency": "WEEKLY",
      "rule": "after",
      "value": 4,
      "totalDeductedAmount": "0",
      "email": "test@gmail.com",
      "customer_id": "696bd627b0c24568ade4675e",
      "mandate_id": "69788a5dd1ed27eeb5fb89d6",
      "mandate_max_amount": 120,
      "amount_variability": "Variable",
      "start_date": "1769507493",
      "session_id": ""
    },
    {
      "status": "ACTIVE",
      "frequency": "WEEKLY",
      "rule": "after",
      "value": 4,
      "totalDeductedAmount": "1000",
      "recurringMandateIds": [
        "6973ad04fa54ee2cf14f438c",
        "697ce750e6446c7babfe4727"
      ],
      "email": "test@gmail.com",
      "customer_id": "696bd627b0c24568ade4675e",
      "mandate_id": "69788d2f0ea4df4fd4e6eb5b",
      "mandate_max_amount": 120,
      "amount_variability": "Variable",
      "start_date": "1769508214",
      "session_id": ""
    },
    {
      "status": "FAILED",
      "frequency": "WEEKLY",
      "rule": "after",
      "value": 4,
      "totalDeductedAmount": "0",
      "email": "test@gmail.com",
      "customer_id": "696bd627b0c24568ade4675e",
      "mandate_id": "697b533b34d180d90cfb2f5f",
      "mandate_max_amount": 120,
      "amount_variability": "Variable",
      "start_date": "1769689915",
      "session_id": ""
    },
    {
      "status": "CREATED",
      "frequency": "WEEKLY",
      "rule": "after",
      "value": 4,
      "totalDeductedAmount": "0",
      "email": "test@gmail.com",
      "customer_id": "696bd627b0c24568ade4675e",
      "mandate_id": "697de0e15d2e562bf8b4552a",
      "mandate_max_amount": 120,
      "amount_variability": "Variable",
      "start_date": "1769857249",
      "session_id": ""
    }
  ]
}
```


# Get Status 4

This API tells you about all the details of a recurring payment which occurred

### Mandatory

you need to pass the `PurchaseID` in the API URL

### Possible Value of Status

| **Status** | **Notes** |
| --- | --- |
| paid | Transaction Successful |
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
async getStatus4(
  purchaseId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success41>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success41`](../../doc/models/success-41.md).

## Example Usage

```ts
const purchaseId = 'purchaseId2';

try {
  const response = await apIsApi.getStatus4(purchaseId);

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
  "purchaseId": "6973ad04fa54ee2cf14f438c",
  "client": {
    "customerId": "NA",
    "email": "sl68792.bravo@bravapay.com",
    "phone": "0557719399",
    "full_name": "Test user",
    "date_of_birth": "2004-07-12",
    "street_address": "10 New Burlington StreetApt. 214",
    "country": "CA",
    "city": "London",
    "zip_code": "W1S 3BE",
    "cc": [],
    "bcc": [],
    "tax_number": "+447755564318",
    "bankAccountNumber": "1345789678",
    "stateCode": "QLD"
  },
  "updated_on": 1769188614,
  "type": "purchase",
  "paymentMethod": "VISA",
  "amountUnit": "MAJOR",
  "errorMsg": "ERROR_PARSING_GROUP_ID",
  "errorCode": "NA",
  "force_recurring": false,
  "created_on": 1769188612,
  "merchantRef": "6973ad04fa54ee2cf14f438c",
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "name": "gaming cards",
        "quantity": 1.0,
        "price": 10.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 10.0,
    "requestAmount": 10.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "taxAmount": 0.0,
    "taxPercent": 0.0,
    "request_client_details": [],
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
    "legal_name": "zenith",
    "brand_name": "zenith",
    "registration_number": "",
    "tax_number": ""
  },
  "transaction_data": {
    "payment_method": "",
    "flow": "payform",
    "extra": {
      "expiry_month": "01",
      "amount": 10.0,
      "card_issuer": "VISION BANK",
      "masked_pan": "42222222*2222",
      "card_brand": "VISA",
      "card_issuer_country": "SA",
      "card_type": "DEBIT",
      "cardholder_name": "fgjhknms",
      "expiry_year": "29"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "49.36.232.107",
        "type": "execute",
        "payment_method": "VISA",
        "flow": "payform",
        "successful": false,
        "country": "VISA",
        "processing_time": 1769188612,
        "extra": {
          "amount": 10.0,
          "masked_pan": "VISA",
          "card_brand": "VISA",
          "card_issuer_country": "VISA",
          "cardholder_name": "Test user"
        },
        "error": {
          "message": "This customer can not be processed !",
          "code": "transaction_error"
        }
      },
      {
        "client_ip": "",
        "type": "execute",
        "payment_method": "VISA",
        "flow": "payform",
        "successful": false,
        "country": "SA",
        "processing_time": 1769188613,
        "extra": {
          "expiry_month": "01",
          "amount": 10.0,
          "card_issuer": "VISION BANK",
          "masked_pan": "42222222*2222",
          "card_brand": "VISA",
          "card_issuer_country": "SA",
          "card_type": "DEBIT",
          "cardholder_name": "fgjhknms",
          "expiry_year": "29"
        },
        "error": {
          "message": "ERROR_PARSING_GROUP_ID",
          "code": "transaction_error"
        }
      }
    ]
  },
  "status": "ERROR",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1769188612
    },
    {
      "status": "pending_execute",
      "timestamp": 1769188612
    },
    {
      "status": "error",
      "timestamp": 1769188613
    },
    {
      "status": "pending_execute",
      "timestamp": 1769188613
    },
    {
      "status": "error",
      "timestamp": 1769188614
    },
    {
      "status": "viewed",
      "timestamp": 1770016552
    }
  ],
  "viewedOn": 1770016552,
  "is_test": false,
  "brand_id": "555c458b-e737-4905-adb2-2451d37cbb6e",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS1841",
  "issued": "2026-01-23",
  "due": 1769188612,
  "refund_upto": 0,
  "cc_descriptor": "",
  "fraudScore": "NA",
  "trustScore": "NA",
  "extraFee": "0",
  "paidOn": 0,
  "receivedAmt": 0.0,
  "taxAmount": 0.0,
  "surcharge": 0.0,
  "surchargeType": "",
  "sessionId": "",
  "refund_availability": "NONE",
  "refundable_amount": 0.0,
  "success_redirect": "https://staging.paysecure.net/getResponse.jsp?issucces=true",
  "failure_redirect": "https://staging.paysecure.net/getResponse.jsp?issucces=false",
  "pending_redirect": "https://staging.paysecure.net/getResponse.jsp?issucces=pending ",
  "cancel_redirect": "",
  "success_callback": "https://www.google.com/",
  "failure_callback": "https://staging.paysecure.net/merchant",
  "platform": "API",
  "created_from_ip": "49.36.232.107",
  "checkout_url": "https://test4.paymentsclub.net/payments/a28ed9974a22a4cbd5f2f49cc26cc334/",
  "direct_post_url": "https://test4.paymentsclub.net/api/v1/p/6973ad04fa54ee2cf14f438c/",
  "payoutProcess": false,
  "payment_type": "internal recurring",
  "mandate_id": "696bc39a7bc779fac5201357"
}
```


# List Saved Cards

## List Saved Cards

Retrieve all saved card tokens for a given customer. Returns the last 4 digits of each card and its associated `token_reference`.

Use this API to display saved cards to the customer for selection before initiating a payment via the S2S API.

### Query Parameters

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| `customerId` | string | Yes | Unique identifier for the customer. Must be URL-encoded if it contains special characters. Email addresses are case-sensitive. |
| `brandId` | string | Yes | Brand id of the merchant |

### Response Fields

| Field | Type | Description |
| --- | --- | --- |
| `card_last_four` | string | Last 4 digits of the stored card. Display to the customer for card selection. |
| `token_reference` | string | Unique reference for this saved card. Pass this in the S2S payment request or Delete Token request. Do not display to the customer. |

### Notes

- The `token_reference` does not expire. It remains valid as long as the saved card has not been deleted.

- Show saved cards to the customer using `card_last_four` alongside a card brand icon (Visa / Mastercard).

- The `token_reference` should only be stored and used server-side.

### Display Tip

Show saved cards using cardlast4 alongside a card brand icon (Visa / Mastercard).  
The token_reference should only be stored and used server-side.

:information_source: **Note** This endpoint does not require authentication.

```ts
async listSavedCards(
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success46[]>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success46[]`](../../doc/models/success-46.md).

## Example Usage

```ts
try {
  const response = await apIsApi.listSavedCards();

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
[
  {
    "card_last_four": "1003",
    "token_reference": "token_2bcf691f0f0347d6bcb38118d1bb31d5"
  },
  {
    "card_last_four": "6006",
    "token_reference": "token_e17dd98c66c14b37afaa62bd4770f915"
  },
  {
    "card_last_four": "6916",
    "token_reference": "token_7178bb7208614544a285656da38ae5ac"
  }
]
```


# Purchase 2

## Purchase

Initiate a payment transaction. This is the standard Paysecure Purchase API.

When a customer completes the purchase on the Paysecure checkout page and opts to save their card, Paysecure provisions a network token in the background and generates a `token_reference` linked to the customer.

### Mandatory Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `client.email` | string | Customer's email address.  <br>Please send it in smallcase |
| `client.city` | string | Customer's city. |
| `client.country` | string | ISO-3166 Alpha-2 country code, uppercase (e.g., IN, US, SG). |
| `client.stateCode` | string | State code, uppercase (e.g., RJ, CA, AL). |
| `client.street_address` | string | Customer's street address. |
| `client.zip_code` | string | Postal / ZIP code. US format: NNNNN or NNNNN-NNNN. |
| `purchase.currency` | string | ISO 4217 currency code (e.g., USD, EUR). Must be enabled on your account. |
| `purchase.products` | array | Array of product objects with `name` and `price`. |
| `brand_id` | string | Your Paysecure Brand ID from Dashboard. |
| `success_redirect` | string | URL to redirect customer after successful payment. |
| `failure_redirect` | string | URL to redirect customer after failed payment. |

### Optional Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `pending_redirect` | string | URL to redirect when payment is pending. |
| `success_callback` | string | Server-to-server webhook URL for success. |
| `failure_callback` | string | Server-to-server webhook URL for failure. |
| `merchantRef` | string | Your internal reference for this transaction. |
| `paymentMethod` | string | Pre-select payment method (e.g., VISA). |
| `client.phone` | string | Customer's phone number. |

### Key Response Fields

| Field | Description |
| --- | --- |
| `id` | Unique purchase ID. |
| `checkout_url` | Redirect customer here to complete payment. Card saving happens during this step. |
| `direct_post_url` | URL for S2S payment submission. |
| `status` | Purchase status. Initially "created". |

#### **Network Tokenisation & Card Saving**

When the customer completes payment via `checkout_url` and opts to save their card, Paysecure provisions a network token. The `token_reference` is then available via the **List Saved Cards** API.

:information_source: **Note** This endpoint does not require authentication.

```ts
async purchase2(
  body: PurchaseRequest3,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success47>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchaseRequest3`](../../doc/models/purchase-request-3.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success47`](../../doc/models/success-47.md).

## Example Usage

```ts
const body: PurchaseRequest3 = {
  client: {
    email: 'customer@example.com',
    country: 'IN',
    city: 'Jaipur',
    stateCode: 'RJ',
    streetAddress: '123 Main Street',
    zipCode: '302001',
    phone: '9999999999',
  },
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'Product Name',
        price: '10.00',
      }
    ],
  },
  brandId: '{{BrandId}}',
  successRedirect: 'https://yoursite.com/success',
  failureRedirect: 'https://yoursite.com/failure',
  pendingRedirect: 'https://yoursite.com/pending',
  successCallback: 'https://yoursite.com/webhook/success',
  failureCallback: 'https://yoursite.com/webhook/failure',
};

try {
  const response = await apIsApi.purchase2(body);

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
  "purchaseId": "69b32e42250ac73495aefd50",
  "client": {
    "customerId": "NA",
    "email": "himanshu1@paysecure.net",
    "full_name": "OpHM",
    "date_of_birth": "1800-01-01",
    "street_address": "SB-124",
    "country": "BR",
    "city": "DLJPR",
    "zip_code": "110001",
    "cc": [],
    "bcc": [],
    "stateCode": "DL"
  },
  "updated_on": 1773350466,
  "type": "purchase",
  "paymentMethod": "MASTER",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "errorCode": "NA",
  "force_recurring": false,
  "created_on": 1773350466,
  "merchantRef": "69b32e42250ac73495aefd50",
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "name": "e-commerce",
        "quantity": 1.0,
        "price": 10.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 10.0,
    "requestAmount": 10.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "taxAmount": 0.0,
    "taxPercent": 0.0,
    "request_client_details": [],
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
    "legal_name": "brand",
    "brand_name": "brand",
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
      "timestamp": 1773350466
    }
  ],
  "is_test": false,
  "brand_id": "5949f2ac-b5a3-4ee4-b585-ad4cf9a6db18",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS1060",
  "issued": "2026-03-12",
  "due": 1773350466,
  "refund_upto": 0,
  "cc_descriptor": "",
  "fraudScore": "NA",
  "trustScore": "NA",
  "extraFee": "0",
  "paidOn": 0,
  "receivedAmt": 0.0,
  "taxAmount": 0.0,
  "surcharge": 0.0,
  "surchargeType": "",
  "sessionId": "",
  "refund_availability": "NONE",
  "refundable_amount": 0.0,
  "success_redirect": "https://google.com/",
  "failure_redirect": "https://facebook.com/",
  "pending_redirect": "https://paysecure.net",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.com",
  "failure_callback": "https://your.failure.callback.com",
  "platform": "API",
  "created_from_ip": "110.235.229.171",
  "checkout_url": "https://api.choicepay.ca/payments/1b73d31d178113798afa0157c8805ef0/",
  "direct_post_url": "https://api.choicepay.ca/api/v1/p/69b32e42250ac73495aefd50/",
  "payoutProcess": false
}
```


# S2 S Payment

## S2S Payment

Process a payment using a saved card's `token_reference`. Paysecure resolves the token reference to the underlying network token and processes the payment securely. If the selected MID does not accept tokens, Paysecure automatically falls back to the card number.

### S2S Input Scenarios

The S2S API accepts different input types depending on the scenario:

| Scenario | What to Send | What Paysecure Does |
| --- | --- | --- |
| **New card** (first-time customer) | Full card details | Paysecure tokenises the card. If the MID supports tokens, the transaction uses the token; otherwise, the card number is used. |
| **Returning customer** (tokenised with Paysecure) | `token_reference` from List Saved Cards | Paysecure uses the stored token and generates a new cryptogram. Falls back to card number if MID doesn't accept tokens. |

### Request Body

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `token_reference` | string | Conditional | Token reference from List Saved Cards. Required when paying with a Paysecure-tokenised card. |
| `cvc` | string | Yes | Card CVC/CVV. **Required even when** **`token_reference`** **is provided**, for 3DS authentication. |
| `remember_card` | string | No | `"on"` to save card, `"off"` to skip. Use `"off"` with saved tokens. |
| `remote_ip` | string | Yes | Cardholder's IP address. |
| `user_agent` | string | Yes | Browser User-Agent string. |
| `accept_header` | string | Yes | Browser Accept header. |
| `language` | string | Yes | Browser language (e.g., `"en-US"`). |
| `java_enabled` | boolean | Yes | Java enabled in browser. |
| `javascript_enabled` | boolean | Yes | JavaScript enabled in browser. |
| `color_depth` | integer | Yes | Screen colour depth. |
| `utc_offset` | integer | Yes | UTC timezone offset (minutes). |
| `screen_width` | integer | Yes | Screen width (px). |
| `screen_height` | integer | Yes | Screen height (px). |

### Token Reference in Response

- **Scenario 1** (New card via S2S): `token_reference` returned in Check Status and Webhook.

- **Scenario 2** (Existing `token_reference`): `token_reference` returned in response and Webhook.

### Important Notes

- CVC is **required** even when using a `token_reference`.

- All browser fields are required for 3D Secure authentication.

- Response follows the standard Paysecure payment response format.

:information_source: **Note** This endpoint does not require authentication.

```ts
async s2SPayment(
  s2S: boolean,
  body: S2SPaymentRequest,
  brandId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success1>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `s2S` | `boolean` | Query, Required | Must be "true" for server-to-server requests. |
| `body` | [`S2SPaymentRequest`](../../doc/models/s2-s-payment-request.md) | Body, Required | - |
| `brandId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success1`](../../doc/models/success-1.md).

## Example Usage

```ts
const s2S = true;

const body: S2SPaymentRequest = {
  tokenReference: 'token_7178aa7208614544a285656da38ae5ac',
  cvc: '791',
  rememberCard: 'off',
  remoteIp: '157.38.242.7',
  userAgent: 'Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/51.0.2704.103 Safari/537.36',
  acceptHeader: 'text/html',
  language: 'en-US',
  javaEnabled: false,
  javascriptEnabled: true,
  colorDepth: 24,
  utcOffset: 0,
  screenWidth: 1920,
  screenHeight: 1080,
};

const brandId = 'brandId4';

try {
  const response = await apIsApi.s2SPayment(
    s2S,
    body,
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
  }
}
```

## Example Response *(as JSON)*

```json
{
  "status": "pending",
  "callback_url": "http://18.214.100.20/api/v1/payment/64b034ecc6dccf7d329d9eb3/",
  "method": "GET"
}
```


# Delete Token

## Delete Token

Permanently delete a saved card and deactivate the associated network token. **This action is irreversible.**

### Path Parameters

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| `token_reference` | string | Yes | The `token_reference` of the saved card to delete. Obtained from the List Saved Cards API. |

### Important Notes

- Deleting a token is **permanent**. The `token_reference` can no longer be used for payments.

- The associated network token is deactivated with the card network.

- If the customer wants to pay with this card again, they will need to re-enter their card details.

### When to Delete

- Customer explicitly requests removal of their saved card.

- GDPR or data retention compliance when a customer closes their account.

- Consider implementing a "Remove Card" option in your account management UI.

:information_source: **Note** This endpoint does not require authentication.

```ts
async deleteToken(
  tokenReference: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success49>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tokenReference` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success49`](../../doc/models/success-49.md).

## Example Usage

```ts
const tokenReference = 'token_reference6';

try {
  const response = await apIsApi.deleteToken(tokenReference);

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
  "message": "Token deleted successfully"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`FailureError`](../../doc/models/failure-error.md) |


# Pay Out 1

## Overview

The **Original Credit Transaction (OCT)**, commonly referred to as **Push to Card**, enables merchants to facilitate near-instantaneous fund transfers directly to a customer’s eligible Visa or Mastercard debit or credit card. Unlike traditional refund processes that can only return funds from a previous purchase, OCT allows for independent disbursements of funds to a cardholder's account.

This feature is designed for high-velocity industries that require frictionless, real-time payouts, such as:

- **Gaming & Betting:** Real-time withdrawal of player winnings.

- **Marketplaces:** Payouts to sellers or service providers.

- **Corporate Disbursements:** Instant insurance claims, rebates, or compensation payments.

- **Merchant Settlements:** Faster access to processed funds for sub-merchants.

By utilizing the Paysecure `/payout` API with the `PAYOUT-CARDS` method, you benefit from a unified orchestration layer that handles the complexities of card network routing, ensuring high success rates and global reach while maintaining the same security standards as your standard payment integrations.

---


## Integration Steps

1. **Enable OCT:** Ensure "Push to Card" permissions are enabled for your merchant account in the Paysecure Merchant Portal.

2. **Collect Card Details:** Use a secure method to collect the recipient's card number and expiry date or can you Paysecure's cashier to do that.

3. **Execute Payout:** Call the `/payout` endpoint with the OCT-specific payout method.

4. **Handle Webhooks:** Listen for the `paid` or `failure` events to update your internal records.

### **Mandatory parameters in the request body:**

| **Parameter** | **Required** | **Notes** |
| --- | --- | --- |
| client.email | Yes | The customer's email.  <br>Please send it in small case. |
| client.phone | Yes | The customer's phone number along with the country code.  <br>Example: +91 9634088651 |
| client.city | Yes | The customer's city. |
| client.country | Yes | ISO-3166 Country Code. Must be upper case. Example “SG” (Alpha2) |
| client.stateCode | Optional | Example “AL”, “XZ”. Must be in upper case. |
| Client.street_address | Optional | The customer's address. |
| client.zip_code | Optional | The customer's ZIP or postal code. If country=US, zip format must be NNNNN or NNNNN-NNNN. |
| currency | Yes | ISO 4217 code for currency you want to send the transaction in.  <br>  <br>Please note, the currency has to be enabled by the account manager for your account. |
| amount | Yes | amount in decimal format.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
| payoutMethod | Optional | example: PAYOUT-CARDS |
| success_redirect | Yes | URL to send the user if the transactions is successful. |
| pending_redirect | Yes | URL to send the user if the transactions is in pending. |
| failure_redirect | Yes | URL to send the user if the transactions is unsuccessful. |
| Purpose | Optional | The purpose of doing a payout. |
| extraParam.token_reference | Yes | Paysecure Token |

Note:

If the merchant is not PCI DSS compliant then they will need to use our **cashier** and we will show the user all the saved cards for him/her. Based on the card chosen, Paysecure will pick up the token_reference from our Back end.

If the merchant is PCI DSS compliant then they can use the payout API and send the token reference as shown above.

:information_source: **Note** This endpoint does not require authentication.

```ts
async payOut1(
  accept: string,
  body: PayOutRequest3,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accept` | `string` | Header, Required | - |
| `body` | [`PayOutRequest3`](../../doc/models/pay-out-request-3.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const accept = 'application/json';

const body: PayOutRequest3 = {
  client: {
    email: 'rahul@gmail.com',
    country: 'GB',
    city: 'London',
    stateCode: 'QLD',
    fullName: 'Rahul Jain',
    streetAddress: '10 New Burlington Street Apt. 214',
    zipCode: 'W1S 3BE',
    phone: '+44 9876543210',
    gender: 'M',
    dateOfBirth: '1970-07-10',
  },
  purpose: 'Testing cards payout',
  currency: 'GBP',
  merchantRef: 'YOUR ORDER ID',
  payoutMethod: 'PAYOUT-CARDS',
  amount: 100,
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  extraParam: {
    tokenReference: 'token_ref',
  },
};

try {
  const response = await apIsApi.payOut1(
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

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | `ApiError` |


# Purchase 3

Use this endpoint to authorise a payment without capturing it. This places a temporary hold on the customer’s funds for the specified amount.

To Initiate a payment, the very first call to make is `/purchases` with the required data in the request body.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.email | The customer's email. |
| client.city | The customer's city. |
| client.country | ISO-3166 Country Code. Must be upper case. Example “SG” (Alpha2) |
| client.stateCode | Example “AL”, “XZ”. Must be in upper case. |
| Client.street_address | The customer's address. |
| client.zip_code | The customer's ZIP or postal code. If country=US, zip format must be NNNNN or NNNNN-NNNN. |
| purchase.currency | ISO 4217 code for currency you want to send the transaction in.  <br>  <br>Please note, the currency has to be enabled by the account manager for your account. |
| purchase.products | An object which contains the list of products which the customer is buying. |
| purchase.products.name | The name of the product. |
| purchase.products.price | Price in decimal format.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
| brand_id | Obtain from Dashboard section of your merchant account login. |
| success_redirect | URL to send the user if the transactions is successful. |
| pending_redirect | URL to send the user if the transactions is in pending. |
| failure_redirect | URL to send the user if the transactions is unsuccessful. |

### **Additional parameters for this usecase:**

| **Parameter** | **Notes** |
| --- | --- |
| skip_capture | true |

## Essential Optional Parameters

### merchantRef

The `merchantRef` parameter, although not mandatory, is strongly advised for merchants to specify. Its inclusion offers two significant advantages for the merchant:

1. **Prevention of Duplicate Requests:** When a `merchantRef` is utilized, it acts as a unique identifier. This means that if a second purchase request is made using the same `merchantRef` (reference number), the system will recognize it and prevent duplicate transactions from occurring. This prevents unintended or duplicate purchases.

2. **Facilitation of Transaction Retrieval:** In situations where the response from the initial purchase request times out or the 'purchaseId' isn't received, having the `merchantRef` allows the merchant to retrieve detailed transaction information. This ensures they can track and access the specific purchase details related to that reference, even if the immediate response was not received.

However, if the merchant does not specify the 'merchantRef' parameter, the platform will automatically assign and use an internal 'purchaseId' as a reference for that transaction.

Upon successul create on a Purchase you'd get a `"purchaseId"` . Use this ID for the next step in Server to server call by calling `p/{purchaseId}/?s2s=true .`

### paymentMethod

The `paymentMethod` parameter identifies which payment solution merchant wants to use to perform a transaction. If parameter is provided, than Paysecure will perform direct payment with the selected payment method instead of loading Paysecure URL.

### Errors

If there are any errors then it'll be in the format of :

```json
{
    "message": "descriptive error message",
    "code": "error_code"
}

```

### Possible Error Messages

| **Error Messages** |
| --- |
| Allowed Limit for this card for particular time period has been consumed |
| some Mandatory Parameter are missing |
| Invalid format of Date_of_Birth \[allowed format: yyyy-mm-dd\] |
| Invalid Email Format |
| Please submit Valid Alpha2 Country Code Ex:(AF,IN) in \\"country\\" parameter |
| Please pass Valid State Code |
| Please pass valid street address in \\"street_address\\" parameter |
| Please pass valid city name in \\"city\\" parameter |
| Please pass valid postal Code name in \\"zip_code\\" parameter |
| You are not Allowed for Live Transaction |
| Merchant Limit is not set |
| Minimum amount is not set for this merchant |
| Brand not found ! |
| Your charges setting is incomplete .Plese Contact to Administrator. |
| Only {{currencyCode}} currency is allowed. |
| Transaction amount must be equal or greater to minimum trans amount |
| Invalid_Parameter  <br>You'd usually get it when one or more mandatory parameters are not present in the request. |

:information_source: **Note** This endpoint does not require authentication.

```ts
async purchase3(
  body: PurchaseRequest4,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Purchase73>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchaseRequest4`](../../doc/models/purchase-request-4.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Purchase73`](../../doc/models/purchase-73.md).

## Example Usage

```ts
const body: PurchaseRequest4 = {
  client: {
    email: 'example@paysecure.net',
    country: 'IN',
    city: '123',
    stateCode: 'ca',
    streetAddress: 'test test',
    zipCode: '234567',
    phone: '+91 9999999999',
  },
  purchase: {
    products: [
      {
        name: 'dk',
        price: '10',
      }
    ],
  },
  status: 'created',
  brandId: 'bd69e8a5-adcf-40de-9e43-2b87cb129a5e',
  skipCapture: true,
  merchantRef: 'd9db7ec0-f94c-4a9d-8883-54c19c222d81',
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
};

try {
  const response = await apIsApi.purchase3(body);

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
  "purchaseId": "64b032c3c6dccf7d329d9e7e",
  "client": {
    "bank_account": "",
    "bank_code": "",
    "email": "dev@paysecure.net",
    "phone": "",
    "full_name": "",
    "date_of_birth": "",
    "personal_code": "",
    "street_address": "test test",
    "country": "IN",
    "city": "123",
    "zip_code": "234567",
    "shipping_street_address": "",
    "shipping_country": "",
    "shipping_city": "",
    "shipping_zip_code": "",
    "cc": [],
    "bcc": [],
    "legal_name": "",
    "brand_name": "",
    "registration_number": "",
    "tax_number": "",
    "stateCode": "ca"
  },
  "updated_on": 1689268934,
  "type": "purchase",
  "force_recurring": false,
  "created_on": 1689268934,
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "name": "dk",
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
    "request_client_details": [],
    "timezone": "America/Edmonton",
    "email_message": ""
  },
  "issuer_details": {
    "website": "",
    "legal_street_address": "",
    "legal_country": "",
    "legal_city": "",
    "legal_zip_code": "",
    "bank_accounts": [
      {
        "bank_account": "",
        "bank_code": ""
      }
    ],
    "legal_name": "shoes",
    "brand_name": "shoes",
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
      "timestamp": 1689268934
    }
  ],
  "is_test": false,
  "brand_id": "bd69e8a5-adcf-40de-9e43-2b87cb129a5e",
  "is_recurring_token": false,
  "reference_generated": "PS161",
  "merchantRef": "d9db7ec0-f94c-4a9d-8883-54c19c222d81",
  "issued": "2023-07-13",
  "due": 1689268934,
  "refund_upto": 0,
  "cc_descriptor": "",
  "refund_availability": "NONE",
  "refundable_amount": 0,
  "success_redirect": "https://your.success.redirect.com",
  "failure_redirect": "https://your.failure.redirect.com",
  "cancel_redirect": "",
  "success_callback": "",
  "platform": "API",
  "created_from_ip": "149.86.53.48",
  "checkout_url": "http://18.214.100.20/payments/64b032c3c6dccf7d329d9e7e/",
  "direct_post_url": "http://18.214.100.20/api/v1/p/64b032c3c6dccf7d329d9e7e/"
}
```


# S2 S1

This API would be the 2nd in sequence to call if the call to `/purchases/` was successful in step 1. and you want to do the transaction via Server-to-Server mode.

The request body would contain the details of the card that's to be transacted upon.

### **Mandatory parameters in request body:**

| Parameter | **Notes** |
| --- | --- |
| remote_ip | IP address of the customer’s device used for transaction. Helps in fraud checks and risk scoring. Ex- 157.38.242.7 |
| user_agent | Full browser and operating system details captured from HTTP header. EX- Chrome/5.0 (X11; Linux x86_64) |
| accept_header | Browser’s accepted content types (from HTTP header). Used for validating request origin and device info. EX- text/html |

**Note:**  
If you want to use token_reference for doing a card transaction, please have a look at Network Tokenisation Section.

### **Essential parameters in request body:**

| Parameter | **Notes** |
| --- | --- |
| cardholder_name | Name of the cardholder |
| card_number | The card numbers Must be 10-20 characters. |
| expires | must be greater than the current month/year. |
| cvc | 3 or 4 digit |

**  
Other optional parameters in request body:**

| Parameter | **Notes** |
| --- | --- |
| language | Preferred language of the user’s browser . EX - en-US |
| java_enabled | Indicates if Java is enabled in the browser. Helps PSPs in device profiling. Ex- true/false |
| javascript_enabled | Indicates if JavaScript is enabled in the client browser. Used for 3DS or risk-based checks. Ex- true |
| color_depth | Bit depth of the display screen. Ex- 24 |
| utc_offset | Difference in minutes between local time and UTC. Used for location and timezone checks. Ex- 330 |
| screen_width | Width of the device screen in pixels. Used in device profiling. Ex- 1920 |
| screen_height | Height of the device screen in pixels. Ex- 1080 |

### Successful Response

If all the details are correct you'll get a 202 response with staus as Pending

```json
{
    "status": "pending",
    "callback_url": "https://paysecure.net/payment/63bd0bf80fb42a076e8a4dd1/",
    "method": "GET"
}

```

If the response code is 202, after receiving the response body, direct the customer to the callback_url provided in the response.

### Errors

If there are any errors then it'll be in the format of :

```json
{
    "message": "descriptive error message",
    "code": "error_code"
}

```

Please see the Status Code section for further details.

| **Error Messages** |
| --- |
| Client Ip could not be matched with Merchant Ip |
| Invalid Card Information |
| Card is Blocked |
| Different Type of key used to create purchase and payment |
| You charges setting is incomplete .Plese Contact to adminstrartor. |
| Allowed Attempt for this Transaction has been consumed |
| Invalid Card Expiry(Valid Format:MM/YY) must be greator than current month/year |
| Customer profile is Blocked |
| Customer/Card not allowed for transaction |

:information_source: **Note** This endpoint does not require authentication.

```ts
async s2S1(
  s2S: boolean,
  body: S2Srequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success1>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `s2S` | `boolean` | Query, Required | - |
| `body` | [`S2Srequest`](../../doc/models/s2-srequest.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success1`](../../doc/models/success-1.md).

## Example Usage

```ts
const s2S = true;

const body: S2Srequest = {
  cardholderName: 'dk',
  cardNumber: '4111111111111111',
  expires: '10/23',
  cvc: '345',
  rememberCard: 'on',
  remoteIp: '157.38.242.7',
  userAgent: 'Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/51.0.2704.103 Safari/537.36',
  acceptHeader: 'text/html',
  language: 'en-US',
  javaEnabled: false,
  javascriptEnabled: true,
  colorDepth: 24,
  utcOffset: 0,
  screenWidth: 1920,
  screenHeight: 1080,
};

try {
  const response = await apIsApi.s2S1(
    s2S,
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
    if (error instanceof FailureError) {
      console.log(error.result);
    }
  }
}
```

## Example Response *(as JSON)*

```json
{
  "status": "pending",
  "callback_url": "http://18.214.100.20/api/v1/payment/64b034ecc6dccf7d329d9eb3/",
  "method": "GET"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | [`FailureError`](../../doc/models/failure-error.md) |


# Capture

After a successful pre-authorisation, use this endpoint to capture (settle) the held funds. You may capture the full authorised amount or a partial amount.

:information_source: **Note** This endpoint does not require authentication.

```ts
async capture(
  body: CaptureRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CaptureRequest`](../../doc/models/capture-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const body: CaptureRequest = {
  merchantReference: '64534345',
};

try {
  const response = await apIsApi.capture(body);

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
    if (error instanceof CaptureError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | Internal Server Error | [`CaptureError`](../../doc/models/capture-error.md) |


# Cancel 1

Use this endpoint to cancel an authorised payment before it has been captured. Voiding releases the held funds back to the customer immediately.

:information_source: **Note** This endpoint does not require authentication.

```ts
async cancel1(requestOptions?: RequestOptions): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
try {
  const response = await apIsApi.cancel1();

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
    if (error instanceof CancelError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 405 | Method Not Allowed | [`CancelError`](../../doc/models/cancel-error.md) |

