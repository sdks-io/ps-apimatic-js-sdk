# Payin AP Is

```ts
const payinApIsApi = new PayinApIsApi(client);
```

## Class Name

`PayinApIsApi`

## Methods

* [Purchases](../../doc/controllers/payin-ap-is.md#purchases)
* [Get Status](../../doc/controllers/payin-ap-is.md#get-status)
* [Create Purchase](../../doc/controllers/payin-ap-is.md#create-purchase)
* [Get Status 1](../../doc/controllers/payin-ap-is.md#get-status-1)
* [Purchases 1](../../doc/controllers/payin-ap-is.md#purchases-1)
* [Purchases 2](../../doc/controllers/payin-ap-is.md#purchases-2)
* [Get Status 2](../../doc/controllers/payin-ap-is.md#get-status-2)
* [Purchases 3](../../doc/controllers/payin-ap-is.md#purchases-3)
* [Get Status 3](../../doc/controllers/payin-ap-is.md#get-status-3)
* [Purchases 4](../../doc/controllers/payin-ap-is.md#purchases-4)
* [Get Status 4](../../doc/controllers/payin-ap-is.md#get-status-4)
* [Payin AP Is](../../doc/controllers/payin-ap-is.md#payin-ap-is)
* [Purchases 5](../../doc/controllers/payin-ap-is.md#purchases-5)
* [Purchases 6](../../doc/controllers/payin-ap-is.md#purchases-6)
* [Get Status 5](../../doc/controllers/payin-ap-is.md#get-status-5)
* [Purchases 7](../../doc/controllers/payin-ap-is.md#purchases-7)
* [Purchases 9](../../doc/controllers/payin-ap-is.md#purchases-9)
* [Purchases 8](../../doc/controllers/payin-ap-is.md#purchases-8)
* [Create Purchase 1](../../doc/controllers/payin-ap-is.md#create-purchase-1)
* [Get Status 6](../../doc/controllers/payin-ap-is.md#get-status-6)


# Purchases

To Initiate a payment, the very first call to make is `/purchases` with the required data in the request body.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) which can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.email | An Identifier for a user |
| client.city | An Identifier for a user |
| client.country | ISO-3166 Country Code. It must be upper case.  <br>This should be "CA" for Interac |
| client.stateCode | Example “AL”, “XZ”.. Must be in upper case. |
| client.street_address |  |
| client.zip_code |  |
| client.phone |  |
| client.full_name |  |
| purchase.currency | ISO 4217 code for currency you want to send the transaction in.  <br>This should be 'CAD' for Interac |
| purchase.products.name | name of the product or service |
| purchase.products.price | Price in decimal format.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
| brand_id | Obtain from Dashboard section of your merchant account login. |
| success_redirect | URL to send the user if the transactions is successful |
| pending_redirect | URL to send the user if the transactions is in progress |
| failure_redirect | URL to send the user if the transactions is UNSUCCESSFUL |

## Optional Parameters

### expireInMin

The `purchase.expireInMin`, when passed in the PayIn request, sets the time window within which a customer should make the Interac payment through their bank's app. If a customer doesn't complete the payment within the configured time window, the status of the payment will be marked as 'EXPIRED' in Paysecure.

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
async purchases(
  body: PurchasesRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PurchaseSuccess>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchasesRequest`](../../doc/models/purchases-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchaseSuccess`](../../doc/models/purchase-success.md).

## Example Usage

```ts
const body: PurchasesRequest = {
  client: {
    email: 'seo2009@test.com',
    streetAddress: '10 New Burlington Street Apt. 214',
    city: 'London',
    fullName: 'Test test',
    zipCode: 'W1S 3BE',
    country: 'CA',
    stateCode: 'QLD',
    phone: '+447755564318',
  },
  purchase: {
    currency: 'CAD',
    expireInMin: '80',
    products: [
      {
        name: 'test ',
        price: 100,
      }
    ],
  },
  paymentMethod: 'INTERAC-ETRANSFER',
  brandId: 'f6aff7d7-bb40-4857-bc84-9b4c8310b043',
  successRedirect: 'https://your.redirect.url/getResponse.jsp?success=true',
  pendingRedirect: 'https://your.redirect.url/getResponse.jsp?success=pending',
  failureRedirect: 'https://your.redirect.url/getResponse.jsp?success=false',
  successCallback: 'https://your.success.callback.url',
  failureCallback: 'https://your.success.failure.url',
};

try {
  const response = await payinApIsApi.purchases(body);

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
  "purchaseId": "67efd0ff97be603f97a3a697",
  "client": {
    "customerId": "NA",
    "email": "ashishm.21190@gmail.com",
    "phone": "+447755564318",
    "full_name": "Test test",
    "date_of_birth": "1970-07-10",
    "street_address": "10 New Burlington Street Apt. 214",
    "country": "CA",
    "city": "London",
    "zip_code": "W1S 3BE",
    "cc": [],
    "bcc": [],
    "gender": "MALE",
    "avatarUrl": "https://res.cloudinary.com/w22/image/upload/v1663783641/photos/currencies/ngn.png",
    "stateCode": "QLD"
  },
  "updated_on": 1743769856,
  "type": "purchase",
  "paymentMethod": "INTERAC-ETRANSFER",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "redirectType": "GET",
  "force_recurring": false,
  "created_on": 1743769855,
  "merchantRef": "67efd0ff97be603f97a3a697",
  "merchantName": "arunsinghal",
  "purchase": {
    "currency": "CAD",
    "products": [
      {
        "name": "test",
        "quantity": 1.0,
        "price": 1.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 1.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "expireInMin": "43200",
    "taxAmount": 0.0,
    "taxPercent": 0.0,
    "request_client_details": [],
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 1.0,
    "currency": "CAD",
    "net_amount": 1.0,
    "fee_amount": 0.0,
    "pending_amount": 0.0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1743769855,
    "remote_paid_on": 1743769855
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
      "amount": 1.0,
      "masked_pan": "INTERAC-ETRANSFER"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "103.59.75.41, 162.158.88.44, 130.176.93.146",
        "type": "execute",
        "payment_method": "INTERAC-ETRANSFER",
        "flow": "payform",
        "successful": true,
        "country": "INTERAC-ETRANSFER",
        "processing_time": 1743769855,
        "extra": {
          "amount": 1.0,
          "masked_pan": "INTERAC-ETRANSFER"
        }
      }
    ]
  },
  "status": "PAYMENT_IN_PROCESS",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1743769855
    },
    {
      "status": "pending_execute",
      "timestamp": 1743769855
    },
    {
      "status": "payment_in_process",
      "timestamp": 1743769856
    },
    {
      "status": "viewed",
      "timestamp": 1744026697
    }
  ],
  "viewedOn": 1744026697,
  "is_test": false,
  "brand_id": "30f7ce6e-3b7e-46a2-9b50-484fc55be689",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS620",
  "issued": "2025-04-04",
  "due": 1743769855,
  "refund_upto": 0,
  "cc_descriptor": "Africhange Technologies",
  "fraudScore": "NA",
  "trustScore": "NA",
  "payInDetails": {
    "name": "INTERAC",
    "emailAddress": "transfer@ieft.ca",
    "secretQA": "66a8c78af1fc2f768304bce4",
    "secretAnswer": "ps8766a8af"
  },
  "paidOn": 0,
  "receivedAmt": 0.0,
  "refund_availability": "NONE",
  "refundable_amount": 0.0,
  "success_redirect": "https://your.redirect.url/getResponse.jsp?success=true",
  "failure_redirect": "https://your.redirect.url/getResponse.jsp?success=false",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.url",
  "failure_callback": "https://your.success.failure.url",
  "platform": "API",
  "created_from_ip": "103.59.75.41, 162.158.88.44, 130.176.93.146",
  "checkout_url": "https://api.choicepay.ca/payments/67efd0ff97be603f97a3a697/",
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
): Promise<ApiResponse<PurchasesSuccess1>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchasesSuccess1`](../../doc/models/purchases-success-1.md).

## Example Usage

```ts
const purchaseId = 'purchaseId2';

try {
  const response = await payinApIsApi.getStatus(purchaseId);

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
  "purchaseId": "6790e75fa46a5a5bb0b00e55",
  "client": {
    "customerId": "NA",
    "email": "ashishm.21190@gmail.com",
    "phone": "+14377717874",
    "full_name": "Test test",
    "date_of_birth": "1970-07-10",
    "street_address": "10 New Burlington Street Apt. 214",
    "country": "CA",
    "city": "London",
    "zip_code": "W1S 3BE",
    "cc": [],
    "bcc": [],
    "gender": "MALE",
    "stateCode": "QLD"
  },
  "updated_on": 1737549752,
  "type": "purchase",
  "paymentMethod": "INTERAC-ETRANSFER",
  "amountUnit": "MAJOR",
  "errorMsg": "Transaction succeeded-APPROVED",
  "redirectType": "GET",
  "force_recurring": false,
  "created_on": 1737549663,
  "merchantRef": "6790e75fa46a5a5bb0b00e55",
  "merchantName": "arunsinghal",
  "purchase": {
    "currency": "CAD",
    "products": [
      {
        "name": "test",
        "quantity": 1,
        "price": 1,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 2,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1,
    "expireInMin": "43200",
    "request_client_details": [],
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 1,
    "currency": "CAD",
    "net_amount": 1,
    "fee_amount": 0,
    "pending_amount": 0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1737549663,
    "remote_paid_on": 1737549663
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
      "amount": 1,
      "masked_pan": "INTERAC-ETRANSFER"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "103.59.75.42, 172.71.186.102, 130.176.183.14",
        "type": "execute",
        "payment_method": "INTERAC-ETRANSFER",
        "flow": "payform",
        "successful": true,
        "country": "INTERAC",
        "processing_time": 1737549663,
        "extra": {
          "amount": 1,
          "masked_pan": "INTERAC-ETRANSFER"
        }
      }
    ]
  },
  "status": "PAID",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1737549663
    },
    {
      "status": "pending_execute",
      "timestamp": 1737549663
    },
    {
      "status": "payment_in_process",
      "timestamp": 1737549664
    },
    {
      "status": "paid 2.0",
      "timestamp": 1737549752
    },
    {
      "status": "viewed",
      "timestamp": 1737549750
    }
  ],
  "viewedOn": 1738749942,
  "is_test": false,
  "brand_id": "30f7ce6e-3b7e-46a2-9b50-484fc55be689",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS376",
  "issued": "2025-01-22",
  "due": 1737549663,
  "refund_upto": 0,
  "cc_descriptor": "Africhange Technologies",
  "fraudScore": "NA",
  "trustScore": "NA",
  "payInDetails": {
    "name": "INTERAC",
    "emailAddress": "deposit@ieft.ca",
    "secretQA": "66a8c78af1fc2f768304bce4",
    "secretAnswer": "ps8766a8af"
  },
  "paidOn": 1737549752,
  "receivedAmt": 2,
  "refund_availability": "NONE",
  "refundable_amount": 0,
  "success_redirect": "https://your.redirect.url/getResponse.jsp?success=true",
  "failure_redirect": "https://your.redirect.url/getResponse.jsp?success=false",
  "cancel_redirect": "",
  "success_callback": "https://webhook.site/83df9776-3590-4e25-9222-870e931ac868",
  "failure_callback": "https://webhook.site/83df9776-3590-4e25-9222-870e931ac868",
  "platform": "API",
  "created_from_ip": "103.59.75.42, 172.71.186.102, 130.176.183.14",
  "checkout_url": "https://api.choicepay.ca/payments/6790e75fa46a5a5bb0b00e55/",
  "payoutProcess": false
}
```


# Create Purchase

To Initiate a payment, the very first call to make is `/purchases` with the required data in the request body.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.email | An Identifier for a user |
| client.city |  |
| client.country | ISO-3166 Country Code. It must be upper case.  <br>This should be "CA" for Interac |
| client.stateCode | Example “AL”, “XZ”.. Must be in upper case. |
| client.street_address |  |
| client.zip_code |  |
| client.phone |  |
| client.full_name |  |
| purchase.currency | ISO 4217 code for currency you want to send the transaction in.  <br>This should be 'CAD' for Interac |
| purchase.products.name |  |
| purchase.products.price | Price in decimal format.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
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
async createPurchase(
  body: CreatePurchaseRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success3>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreatePurchaseRequest`](../../doc/models/create-purchase-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success3`](../../doc/models/success-3.md).

## Example Usage

```ts
const body: CreatePurchaseRequest = {
  client: {
    email: 'ashishm.21190@gmail.com',
    country: 'CA',
    city: 'London',
    stateCode: 'QLD',
    fullName: 'Test test',
    streetAddress: '10 New Burlington Street Apt. 214',
    zipCode: 'W1S 3BE',
    phone: '+447755564318',
    gender: 'MALE',
    dateOfBirth: '1970-07-10',
  },
  purchase: {
    currency: 'CAD',
    products: [
      {
        name: 'test ',
        price: 1,
      }
    ],
  },
  paymentMethod: 'INTERAC-REQUEST-MONEY',
  brandId: '0cea7af3-23b2-4278-ab94-acf4076cbee4',
  successRedirect: 'https://your.redirect.url/getResponse',
  failureRedirect: 'https://your.redirect.url/getResponse',
  successCallback: 'https://your.success.callback.url',
  failureCallback: 'https://your.success.failure.url',
};

try {
  const response = await payinApIsApi.createPurchase(body);

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
  "purchaseId": "670cb0affcc7f4706acb65e0",
  "client": {
    "email": "ashishm.21190@gmail.com",
    "phone": "+447755564318",
    "full_name": "Test test",
    "date_of_birth": "1970-07-10",
    "street_address": "10 New Burlington Street Apt. 214",
    "country": "CA",
    "city": "London",
    "zip_code": "W1S 3BE",
    "cc": [],
    "bcc": [],
    "gender": "MALE",
    "avatarUrl": "https://res.cloudinary.com/w22/image/upload/v1663783641/photos/currencies/ngn.png",
    "stateCode": "QLD"
  },
  "updated_on": 1728884911,
  "type": "purchase",
  "paymentMethod": "INTERAC-REQUEST-MONEY",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "redirectType": "POST",
  "force_recurring": false,
  "created_on": 1728884911,
  "merchantRef": "670cb0affcc7f4706acb65e0",
  "merchantName": "ajay03",
  "purchase": {
    "currency": "CAD",
    "products": [
      {
        "name": "test",
        "quantity": 1,
        "price": 1,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 1,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1,
    "expireInMin": "1440",
    "request_client_details": [],
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 1,
    "currency": "CAD",
    "net_amount": 1,
    "fee_amount": 0,
    "pending_amount": 0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1728884911,
    "remote_paid_on": 1728884911
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
    "legal_name": "r4",
    "brand_name": "r4",
    "registration_number": "",
    "tax_number": ""
  },
  "transaction_data": {
    "payment_method": "",
    "flow": "payform",
    "extra": {
      "amount": 1,
      "masked_pan": "INTERAC-DEBIT"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "110.235.229.9",
        "type": "execute",
        "payment_method": "INTERAC-DEBIT",
        "flow": "payform",
        "successful": true,
        "country": "INTERAC-DEBIT",
        "processing_time": 1728884911,
        "extra": {
          "amount": 1,
          "masked_pan": "INTERAC-DEBIT"
        }
      }
    ]
  },
  "status": "PAYMENT_IN_PROCESS",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1728884911
    },
    {
      "status": "pending_execute",
      "timestamp": 1728884911
    },
    {
      "status": "payment_in_process",
      "timestamp": 1728884911
    }
  ],
  "is_test": false,
  "brand_id": "0cea7af3-23b2-4278-ab94-acf4076cbee4",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS3",
  "issued": "2024-10-14",
  "due": 1728884911,
  "refund_upto": 1744433315,
  "cc_descriptor": "",
  "fraudScore": "NA",
  "trustScore": "NA",
  "refund_availability": "NONE",
  "refundable_amount": 1,
  "success_redirect": "https://your.redirect.url/getResponse.jsp?success=true",
  "failure_redirect": "https://your.redirect.url/getResponse.jsp?success=false",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.url",
  "failure_callback": "https://your.success.failure.url",
  "platform": "API",
  "created_from_ip": "110.235.229.9",
  "checkout_url": "https://api.paysecure.net/payments/670cb0affcc7f4706acb65e0/",
  "payoutProcess": false
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
): Promise<ApiResponse<Success3>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success3`](../../doc/models/success-3.md).

## Example Usage

```ts
const purchaseId = 'purchaseId2';

try {
  const response = await payinApIsApi.getStatus1(purchaseId);

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
  "purchaseId": "670cb0affcc7f4706acb65e0",
  "client": {
    "email": "ashishm.21190@gmail.com",
    "phone": "+447755564318",
    "full_name": "Test test",
    "date_of_birth": "1970-07-10",
    "street_address": "10 New Burlington Street Apt. 214",
    "country": "CA",
    "city": "London",
    "zip_code": "W1S 3BE",
    "cc": [],
    "bcc": [],
    "gender": "MALE",
    "avatarUrl": "https://res.cloudinary.com/w22/image/upload/v1663783641/photos/currencies/ngn.png",
    "stateCode": "QLD"
  },
  "updated_on": 1728884911,
  "type": "purchase",
  "paymentMethod": "INTERAC-REQUEST-MONEY",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "redirectType": "POST",
  "force_recurring": false,
  "created_on": 1728884911,
  "merchantRef": "670cb0affcc7f4706acb65e0",
  "merchantName": "ajay03",
  "purchase": {
    "currency": "CAD",
    "products": [
      {
        "name": "test",
        "quantity": 1,
        "price": 1,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 1,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1,
    "expireInMin": "1440",
    "request_client_details": [],
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 1,
    "currency": "CAD",
    "net_amount": 1,
    "fee_amount": 0,
    "pending_amount": 0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1728884911,
    "remote_paid_on": 1728884911
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
    "legal_name": "r4",
    "brand_name": "r4",
    "registration_number": "",
    "tax_number": ""
  },
  "transaction_data": {
    "payment_method": "",
    "flow": "payform",
    "extra": {
      "amount": 1,
      "masked_pan": "INTERAC-DEBIT"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "110.235.229.9",
        "type": "execute",
        "payment_method": "INTERAC-DEBIT",
        "flow": "payform",
        "successful": true,
        "country": "INTERAC-DEBIT",
        "processing_time": 1728884911,
        "extra": {
          "amount": 1,
          "masked_pan": "INTERAC-DEBIT"
        }
      }
    ]
  },
  "status": "PAID",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1728884911
    },
    {
      "status": "pending_execute",
      "timestamp": 1728884911
    },
    {
      "status": "payment_in_process",
      "timestamp": 1728884911
    },
    {
      "status": "paid",
      "timestamp": 1728884911
    }
  ],
  "is_test": false,
  "brand_id": "0cea7af3-23b2-4278-ab94-acf4076cbee4",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS3",
  "issued": "2024-10-14",
  "due": 1728884911,
  "refund_upto": 1744433315,
  "cc_descriptor": "",
  "fraudScore": "NA",
  "trustScore": "NA",
  "refund_availability": "NONE",
  "refundable_amount": 1,
  "success_redirect": "https://your.redirect.url/getResponse.jsp?success=true",
  "failure_redirect": "https://your.redirect.url/getResponse.jsp?success=false",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.url",
  "failure_callback": "https://your.success.failure.url",
  "platform": "API",
  "created_from_ip": "110.235.229.9",
  "checkout_url": "https://api.paysecure.net/payments/670cb0affcc7f4706acb65e0/",
  "payoutProcess": false
}
```


# Purchases 1

To Initiate a payment, the very first call to make is `/purchases` with the required data in the request body.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.email | An Identifier for a user |
| client.city | An Identifier for a user |
| client.country | ISO-3166 Country Code. It must be upper case.  <br>This should be "CA" for Interac |
| client.stateCode | Example “AL”, “XZ”.. Must be in upper case. |
| client.street_address |  |
| client.zip_code |  |
| client.phone |  |
| client.full_name |  |
| purchase.currency | ISO 4217 code for currency you want to send the transaction in.  <br>This should be 'CAD' for Interac |
| purchase.products.name | name of the product or service |
| purchase.products.price | Price in decimal format.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
| brand_id | Obtain from Dashboard section of your merchant account login. |
| success_redirect | URL to send the user if the transactions is successful |
| pending_redirect | URL to send the user if the transactions is in progress |
| failure_redirect | URL to send the user if the transactions is UNSUCCESSFUL |

## Optional Parameters

### expireInMin

The `purchase.expireInMin`, when passed in the PayIn request, sets the time window within which a customer should make the Interac payment through their bank's app. If a customer doesn't complete the payment within the configured time window, the status of the payment will be marked as 'EXPIRED' in Paysecure.

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
async purchases1(
  body: PurchasesRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PurchaseSuccess1>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchasesRequest`](../../doc/models/purchases-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchaseSuccess1`](../../doc/models/purchase-success-1.md).

## Example Usage

```ts
const body: PurchasesRequest = {
  client: {
    email: 'seo2009@test.com',
    streetAddress: '10 New Burlington Street Apt. 214',
    city: 'London',
    fullName: 'Test Customer',
    zipCode: 'W1S 3BE',
    country: 'CA',
    stateCode: 'QLD',
    phone: '+447755564318',
  },
  purchase: {
    currency: 'CAD',
    expireInMin: '80',
    products: [
      {
        name: 'test ',
        price: 100,
      }
    ],
  },
  paymentMethod: 'INTERAC-EXPRESS',
  brandId: 'f6aff7d7-bb40-4857-bc84-9b4c8310b043',
  successRedirect: 'https://your.redirect.url/getResponse.jsp?success=true',
  pendingRedirect: 'https://tyour.redirect.url/getResponse.jsp?success=pending',
  failureRedirect: 'https://your.redirect.url/getResponse.jsp?success=false',
  successCallback: 'https://your.success.callback.url',
  failureCallback: 'https://your.success.failure.url',
};

try {
  const response = await payinApIsApi.purchases1(body);

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
  "purchaseId": "6890aba7faa4173bbbbb76c6",
  "client": {
    "customerId": "NA",
    "email": "seo2009@test.com",
    "phone": "+447755564318",
    "full_name": "Test test",
    "date_of_birth": "1970-07-10",
    "street_address": "10 New Burlington Street Apt. 214",
    "country": "CA",
    "city": "London",
    "zip_code": "W1S 3BE",
    "cc": [],
    "bcc": [],
    "stateCode": "QLD"
  },
  "updated_on": 1754311599,
  "type": "purchase",
  "paymentMethod": "INTERAC-EXPRESS",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "redirectType": "GET",
  "force_recurring": false,
  "created_on": 1754311591,
  "extraParam": {
    "reference": "wkdjabf43"
  },
  "merchantRef": "6890aba7faa4173bbbbb76c6",
  "merchantName": "arunsinghal",
  "purchase": {
    "currency": "CAD",
    "products": [
      {
        "name": "test",
        "quantity": 1.0,
        "price": 100.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 100.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "expireInMin": "1440",
    "taxAmount": 0.0,
    "taxPercent": 0.0,
    "request_client_details": [],
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 100.0,
    "currency": "CAD",
    "net_amount": 100.0,
    "fee_amount": 0.0,
    "pending_amount": 0.0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1754311592,
    "remote_paid_on": 1754311592
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
      "amount": 100.0,
      "masked_pan": "INTERAC-EXPRESS"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "103.59.75.176, 104.23.216.90, 18.68.12.74",
        "type": "execute",
        "payment_method": "INTERAC-EXPRESS",
        "flow": "payform",
        "successful": true,
        "country": "INTERAC-EXPRESS",
        "processing_time": 1754311592,
        "extra": {
          "amount": 100.0,
          "masked_pan": "INTERAC-EXPRESS"
        }
      }
    ]
  },
  "status": "PAYMENT_IN_PROCESS",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1754311591
    },
    {
      "status": "pending_execute",
      "timestamp": 1754311592
    },
    {
      "status": "payment_in_process",
      "timestamp": 1754311599
    }
  ],
  "is_test": false,
  "brand_id": "30f7ce6e-3b7e-46a2-9b50-484fc55be689",
  "is_recurring_token": false,
  "reference_generated": "PS1060",
  "issued": "2025-08-04",
  "due": 1754311591,
  "refund_upto": 0,
  "cc_descriptor": "",
  "fraudScore": "0",
  "trustScore": "0",
  "payInDetails": {
    "name": "INTERAC E-TRANSFER",
    "emailAddress": "fund@ieft.ca",
    "reference_number": "8g1lya"
  },
  "paidOn": 0,
  "receivedAmt": 0.0,
  "refund_availability": "NONE",
  "refundable_amount": 0.0,
  "success_redirect": "https://your.success.redirect.com",
  "failure_redirect": "https://your.failure.redirect.com",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.com",
  "failure_callback": "https://your.failure.callback.com",
  "platform": "API",
  "created_from_ip": "103.59.75.176, 104.23.216.90, 18.68.12.74",
  "checkout_url": "https://api.choicepay.ca/payments/6890aba7faa4173bbbbb76c6/",
  "payoutProcess": false
}
```


# Purchases 2

To Initiate a payment, the very first call to make is `/purchases` with the required data in the request body.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Request Body Parameters:**

| **Parameter** | **Notes** |
| --- | --- |
| client.full_name | Conditional.  <br>But Recommended to pass the complete name of the client. Atleast 2 words recommended. |
| client.email | Conditional.  <br>But Recommended to pass a correct email id. |
| client.tax_number | Mandatory.  <br>Pass the CPF (Brazilian tax identification number of customer), must contain 11 digits. |
| paymentMethod | Conditional.  <br>Mandatory if you are not using Paysecure Cashier. Else Non Mandatory.  <br>Value: PIX |
| purchase.currency | Mandatory.  <br>ISO 4217 code for currency you want to send the transaction in. This should be 'BRL' for PIX. |
| purchase.products.name | Mandatory. |
| purchase.products.price | Mandatory.  <br>Price in decimal format upto 2 decimals.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
| brand_id | Mandatory.  <br>Obtain from Dashboard section of your merchant account login. |
| success_redirect | Mandatory.  <br>URL to send the user if the transactions is successful. |
| pending_redirect | Mandatory.  <br>URL to send the user if the transactions is in progress state. |
| failure_redirect | Mandatory  <br>URL to send the user if the transactions has failed. |

**Note:** the object “pix_payload.payload” contains all the necessary fields to create a page containing a QR code and other information on the merchant portal. The field “pix_payload.qr_code” value is in Base64. This can be used to show the QR code image. The field "pix_payload.expiration_date" is in UTC time.

## Essential Optional Parameters

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
| Allowed Limit for this card for particular time period has been consumed |  |
| some Mandatory Parameter are missing |  |
| Invalid format of Date_of_Birth\[allowed format: yyyy-mm-dd\] |  |
| Invalid Email Format |  |
| Please submit Valid Alpha2 Country Code Ex:(AF,IN) in \\"country\\" parameter |  |
| Please pass Valid State Code |  |
| Please pass valid street address in \\"street_address\\" parameter |  |
| Please pass valid city name in \\"city\\" parameter |  |
| Please pass valid postal Code name in \\"zip_code\\" parameter |  |
| You are not Allowed for Live Transaction |  |
| Merchant Limit is not set |  |
| Minimum amount is not set for this merchant |  |
| Brand not found! |  |
| Your charges setting is incomplete .Plese Contact to Administrator. |  |
| Only `“{curr_name}"` currency is allowed |  |
| Transaction amount must be equal or greater to minimum trans amount |  |
| Invalid_Parameter | You'd usually get it when one or more mandatory parameters are not present in the request. |

:information_source: **Note** This endpoint does not require authentication.

```ts
async purchases2(
  body: PurchasesRequest2,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PurchaseSuccess2>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchasesRequest2`](../../doc/models/purchases-request-2.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchaseSuccess2`](../../doc/models/purchase-success-2.md).

## Example Usage

```ts
const body: PurchasesRequest2 = {
  client: {
    email: 'test@gmail.com',
    fullName: 'test test',
    country: 'BR',
    city: 'Brasília',
    stateCode: 'SP',
    streetAddress: 'Praça da Bíblia 1308',
    zipCode: '57312-140',
    dateOfBirth: '1994-31-04',
    phone: '+558262362732',
    taxNumber: '39933551809',
  },
  purchase: {
    currency: 'BRL',
    products: [
      {
        name: 'test ',
        price: 10,
      }
    ],
  },
  paymentMethod: 'PIX',
  merchantRef: 'test12',
  brandId: '90ed108b-6753-465d-8a21-e2cc604ff814',
  successRedirect: 'https://test.com/getResponse.jsp?success=true',
  pendingRedirect: 'https://test.com/getResponse.jsp?success=pending',
  failureRedirect: 'https://test.com/getResponse.jsp?success=false',
  successCallback: 'https://test1.com',
  failureCallback: 'https://test2.com',
};

try {
  const response = await payinApIsApi.purchases2(body);

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
  "purchaseId": "65f9368cb905381ba207b3c4",
  "client": {
    "email": "test@gmail.com",
    "full_name": "test test",
    "country": "BR",
    "city": "Brasília",
    "stateCode": "SP",
    "street_address": "Praça da Bíblia 1308",
    "zip_code": "57312-140",
    "date_of_birth": "1994-31-04",
    "phone": "+558262362732",
    "tax_number": "39933551809"
  },
  "updated_on": 1710831244,
  "type": "purchase",
  "paymentMethod": "PIX",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "redirectType": "POST",
  "force_recurring": false,
  "created_on": 1710831244,
  "merchantRef": "65f9368cb905381ba207b3c4",
  "merchantName": "test",
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "price": 10
      }
    ],
    "total": 10,
    "language": "en",
    "total_formatted": 1,
    "timezone": "MIT"
  },
  "issuer_details": {
    "bank_accounts": [
      {
        "bank_account": "",
        "bank_code": ""
      }
    ],
    "legal_name": "newbrand",
    "brand_name": "newbrand"
  },
  "transaction_data": {},
  "status": "CREATED",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1764922723
    },
    {
      "status": "pending_execute",
      "timestamp": 1764922723
    },
    {
      "status": "payment_in_process",
      "timestamp": 1764922727
    }
  ],
  "pix_payload": {
    "payload": "00020101021226800014br.gov.bcb.pix2558pix.asaas.com/qr/cobv/e3eb36eb-7e9b-404d-9bd3-b486a42da3445204000053039865802BR5925A55 CONSULTORIA EM CREDIT6009Sao Paulo61080455202062070503***630451CA",
    "qr_code": "iVBORw0KGgoAAAANSUhEUgAAAZ8AAAGfCAIAAAAPgEjDAAAP4UlEQVR42u3bUY7cSA4EUN … ..",
    "expiration_date": "2025-03-27 23:59:59"
  },
  "is_test": false,
  "brand_id": "90ed108b-6753-465d-8a21-e2cc604ff814",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS2696",
  "issued": "2024-03-19",
  "due": 1710831244,
  "refund_upto": 0,
  "cc_descriptor": "",
  "fraudScore": "NA",
  "trustScore": "NA",
  "refund_availability": "NONE",
  "refundable_amount": 0,
  "success_redirect": "https://test.com/getResponse.jsp?success=true",
  "pending_redirect": "https://test.com/getResponse.jsp?success=pending",
  "failure_redirect": "https://test.com/getResponse.jsp?success=false",
  "success_callback": "https://test1.com",
  "failure_callback": "https://test2.com",
  "platform": "API",
  "created_from_ip": "183.83.53.0",
  "checkout_url": "https://api.choicepay.ca/payments/33ddc21c6073a7ac722288f0b2ec35be/",
  "payoutProcess": false
}
```


# Get Status 2

This API tells you about all the details of a purchase, including its history

### Mandatory

you need to pass the `PurchaseID` in the API URL

### Possible Value of Status

| **Status** | **Notes** |
| --- | --- |
| paid | Transaction Successful |
| payment_in_process | Payment is under Processing |
| expired | The purchase has Expired. |
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
): Promise<ApiResponse<Success7>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success7`](../../doc/models/success-7.md).

## Example Usage

```ts
const purchaseId = 'purchaseId2';

try {
  const response = await payinApIsApi.getStatus2(purchaseId);

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
  "purchaseId": "65f9368cb905381ba207b3c4",
  "client": {
    "email": "test@gmail.com",
    "full_name": "Test test",
    "tax_number": "39933551809"
  },
  "updated_on": 1710831244,
  "type": "purchase",
  "paymentMethod": "PIX",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "redirectType": "POST",
  "force_recurring": false,
  "created_on": 1710831244,
  "merchantRef": "65f9368cb905381ba207b3c4",
  "merchantName": "test",
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "price": 10.0
      }
    ],
    "total": 10.0,
    "language": "en",
    "total_formatted": 1.0,
    "timezone": "MIT"
  },
  "issuer_details": {
    "bank_accounts": [
      {
        "bank_account": "",
        "bank_code": ""
      }
    ],
    "legal_name": "newbrand",
    "brand_name": "newbrand"
  },
  "transaction_data": {},
  "status": "CREATED",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1710831244
    }
  ],
  "is_test": false,
  "brand_id": "90ed108b-6753-465d-8a21-e2cc604ff814",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS2696",
  "issued": "2024-03-19",
  "due": 1710831244,
  "refund_upto": 0,
  "cc_descriptor": "",
  "fraudScore": "NA",
  "trustScore": "NA",
  "refund_availability": "NONE",
  "refundable_amount": 0.0,
  "success_redirect": "https://test.com/getResponse.jsp?success=true",
  "pending_redirect": "https://test.com/getResponse.jsp?success=pending",
  "failure_redirect": "https://test.com/getResponse.jsp?success=false",
  "cancel_redirect": "",
  "success_callback": "https://test1.com",
  "failure_callback": "https://test2.com",
  "platform": "API",
  "created_from_ip": "223.182.100.34",
  "checkout_url": "https://api.paysecure.net/payments/65f9368cb905381ba207b3c4/"
}
```


# Purchases 3

To Initiate a payment, the very first call to make is `/purchases` with the required data in the request body.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.email | An Identifier for a user |
| client.city |  |
| client.country | ISO-3166 Country Code. It must be upper case. Example “SG” (Alpha2) |
| client.stateCode | Example “AL”, “XZ”.. Must be in upper case. |
| client.street_address |  |
| client.zip_code |  |
| client.phone |  |
| client.full_name |  |
| purchase.currency | ISO 4217 code for currency you want to send the transaction in.  <br>Please note, the currency has to be enbaled by the account manager for your account. |
| purchase.products.name |  |
| purchase.products.price | Price in decimal format.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
| brand_id | Obtain from Dashboard section of your merchant account login. |
| success_redirect | URL to send the user if the transactions is successful |
| failure_redirect | URL to send the user if the transactions is UNSUCCESSFUL |

## Optional Parameters

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
async purchases3(
  body: PurchasesRequest3,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PurchaseSuccess3>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchasesRequest3`](../../doc/models/purchases-request-3.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchaseSuccess3`](../../doc/models/purchase-success-3.md).

## Example Usage

```ts
const body: PurchasesRequest3 = {
  client: {
    email: 'DEEPAKDEEPAKSINGHAL@gmail.com',
    streetAddress: '10 New Burlington Street Apt. 214',
    city: 'London',
    fullName: 'Test test',
    zipCode: 'W1S 3BE',
    country: 'EG',
    stateCode: 'QLD',
    phone: '+447755564318',
  },
  purchase: {
    currency: 'EGP',
    products: [
      {
        name: 'test ',
        price: 10,
      }
    ],
  },
  paymentMethod: 'FawryPay',
  brandId: '{{brand_id}}',
  successRedirect: 'https://your.success.redirect.com/getResponse.jsp?success=true',
  pendingRedirect: 'https://staging.paysecure.net/getResponse.jsp?success=true',
  failureRedirect: 'https://your.failure.redirect.com/getResponse.jsp?success=false',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
};

try {
  const response = await payinApIsApi.purchases3(body);

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
  "purchaseId": "667cfb2cf0bd8d672c8fc562",
  "client": {
    "email": "deepakdeepaksinghal@gmail.com",
    "phone": "+447755564318",
    "full_name": "Test test",
    "date_of_birth": "1970-07-10",
    "street_address": "10 New Burlington Street Apt. 214",
    "country": "EG",
    "city": "London",
    "zip_code": "W1S 3BE",
    "cc": [],
    "bcc": [],
    "stateCode": "QLD"
  },
  "updated_on": 1719466796,
  "type": "purchase",
  "paymentMethod": "FAWRYPAY",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "redirectType": "POST",
  "force_recurring": false,
  "created_on": 1719466796,
  "merchantRef": "667cfb2cf0bd8d672c8fc562",
  "instruction": "Please use the reference number 9350804722 to pay 10 EGP for this order at Fawrypay store. Complete the payment before 6/29/2024 5:39:59 AM +00:00",
  "merchantName": "merchant002",
  "purchase": {
    "currency": "EGP",
    "products": [
      {
        "name": "test",
        "quantity": 1.0,
        "price": 10.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 10.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "request_client_details": [],
    "timezone": "MIT",
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 10.0,
    "currency": "EGP",
    "net_amount": 10.0,
    "fee_amount": 0.0,
    "pending_amount": 0.0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1719466796,
    "remote_paid_on": 1719466796
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
      "amount": 10.0,
      "masked_pan": "FAWRYPAY"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "110.235.229.106",
        "type": "execute",
        "payment_method": "FAWRYPAY",
        "flow": "payform",
        "successful": true,
        "country": "FAWRYPAY",
        "processing_time": 1719466796,
        "extra": {
          "amount": 10.0,
          "masked_pan": "FAWRYPAY"
        }
      }
    ]
  },
  "status": "PAYMENT_IN_PROCESS",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1719466796
    },
    {
      "status": "pending_execute",
      "timestamp": 1719466796
    },
    {
      "status": "payment_in_process",
      "timestamp": 1719466796
    }
  ],
  "is_test": false,
  "brand_id": "c4003b2c-22d4-4dc1-ad0c-c6b54f8c9636",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS10252",
  "issued": "2024-06-27",
  "due": 1719466796,
  "refund_upto": 1735015199,
  "cc_descriptor": "",
  "fraudScore": "NA",
  "trustScore": "NA",
  "payInDetails": {
    "reference_number": "9350804722",
    "payment_method": "PAYATFAWRY",
    "transaction_expiry": "29 Jun 2024 05:39:59:054 +0000"
  },
  "refund_availability": "NONE",
  "refundable_amount": 10.0,
  "success_redirect": "https://your.success.redirect.com/getResponse.jsp?success=true",
  "failure_redirect": "https://your.failure.redirect.com/getResponse.jsp?success=false",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.com",
  "failure_callback": "https://your.failure.callback.com",
  "platform": "API",
  "created_from_ip": "110.235.229.106",
  "checkout_url": "https://api.paysecure.net/payments/667cfb2cf0bd8d672c8fc562/"
}
```


# Get Status 3

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
async getStatus3(
  purchaseId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PurchasesSuccess2>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchasesSuccess2`](../../doc/models/purchases-success-2.md).

## Example Usage

```ts
const purchaseId = 'purchaseId2';

try {
  const response = await payinApIsApi.getStatus3(purchaseId);

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
  "purchaseId": "667cfc59f0bd8d672c8fc6c8",
  "client": {
    "email": "deepakdeepaksinghal@gmail.com",
    "phone": "+447755564318",
    "full_name": "Test test",
    "date_of_birth": "1970-07-10",
    "street_address": "10 New Burlington Street Apt. 214",
    "country": "EG",
    "city": "London",
    "zip_code": "W1S 3BE",
    "cc": [],
    "bcc": [],
    "stateCode": "QLD"
  },
  "updated_on": 1719467097,
  "type": "purchase",
  "paymentMethod": "FAWRYPAY",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "redirectType": "POST",
  "force_recurring": false,
  "created_on": 1719467097,
  "merchantRef": "667cfc59f0bd8d672c8fc6c8",
  "instruction": "Please use the reference number 9350717665 to pay 10 EGP for this order at Fawrypay store. Complete the payment before 6/29/2024 5:45:00 AM +00:00",
  "merchantName": "merchant002",
  "purchase": {
    "currency": "EGP",
    "products": [
      {
        "name": "test",
        "quantity": 1.0,
        "price": 10.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 10.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "request_client_details": [],
    "timezone": "MIT",
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 10.0,
    "currency": "EGP",
    "net_amount": 10.0,
    "fee_amount": 0.0,
    "pending_amount": 0.0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1719467097,
    "remote_paid_on": 1719467097
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
      "amount": 10.0,
      "masked_pan": "FAWRYPAY"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "110.235.229.106",
        "type": "execute",
        "payment_method": "FAWRYPAY",
        "flow": "payform",
        "successful": true,
        "country": "FAWRYPAY",
        "processing_time": 1719467097,
        "extra": {
          "amount": 10.0,
          "masked_pan": "FAWRYPAY"
        }
      }
    ]
  },
  "status": "PAYMENT_IN_PROCESS",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1719467097
    },
    {
      "status": "pending_execute",
      "timestamp": 1719467097
    },
    {
      "status": "payment_in_process",
      "timestamp": 1719467097
    },
    {
      "status": "viewed",
      "timestamp": 1719467160
    }
  ],
  "viewedOn": 1719467160,
  "is_test": false,
  "brand_id": "c4003b2c-22d4-4dc1-ad0c-c6b54f8c9636",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS10253",
  "issued": "2024-06-27",
  "due": 1719467097,
  "refund_upto": 1735015500,
  "cc_descriptor": "",
  "fraudScore": "NA",
  "trustScore": "NA",
  "payInDetails": {
    "reference_number": "9350717665",
    "payment_method": "PAYATFAWRY",
    "transaction_expiry": "29 Jun 2024 05:45:00:245 +0000"
  },
  "refund_availability": "NONE",
  "refundable_amount": 10.0,
  "success_redirect": "https://your.success.redirect.com/getResponse.jsp?success=true",
  "failure_redirect": "https://your.failure.redirect.com/getResponse.jsp?success=false",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.com",
  "failure_callback": "https://your.failure.callback.com",
  "platform": "API",
  "created_from_ip": "110.235.229.106",
  "checkout_url": "https://api.paysecure.net/payments/667cfb2cf0bd8d672c8fc562/"
}
```


# Purchases 4

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

Possible Payment Methods allowed: UPI-QR and UPI-INTENT

### Possible Error Messages

| **Error Messages** |
| --- |
| Allowed Limit for this payment method for particular time period has been consumed |
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
async purchases4(
  body: PurchasesRequest4,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchasesRequest4`](../../doc/models/purchases-request-4.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const body: PurchasesRequest4 = {
  client: {
    email: 'test@gmail.com',
    streetAddress: 'Praça da Bíblia 1308',
    city: 'Jaipur',
    fullName: 'test test',
    zipCode: '302022',
    country: 'IN',
    dateOfBirth: '1994-31-04',
    stateCode: 'RJ',
    phone: '+91 9634988765',
  },
  purchase: {
    currency: 'INR',
    products: [
      {
        name: 'test',
        price: 100,
      }
    ],
  },
  paymentMethod: 'UPI-QR',
  merchantRef: 'test12',
  brandId: '{{merchant_brand_id}}',
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
};

try {
  const response = await payinApIsApi.purchases4(body);

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
"{\r\n    \"purchaseId\": \"6682942d5273633e7b8d30c8\",\r\n    \"client\": {\r\n        \"email\": \"deepakdeepaksinghal@gmail.com\",\r\n        \"date_of_birth\": \"1970-07-10\",\r\n        \"street_address\": \"10 New Burlington Street Apt. 214\",\r\n        \"country\": \"EG\",\r\n        \"city\": \"London\",\r\n        \"zip_code\": \"W1S 3BE\",\r\n        \"cc\": [],\r\n        \"bcc\": [],\r\n        \"stateCode\": \"QLD\"\r\n    },\r\n    \"updated_on\": 1719833645,\r\n    \"type\": \"purchase\",\r\n    \"paymentMethod\": \"UPI-QR\",\r\n    \"amountUnit\": \"MAJOR\",\r\n    \"errorMsg\": \"\",\r\n    \"redirectType\": \"POST\",\r\n    \"force_recurring\": false,\r\n    \"created_on\": 1719833645,\r\n    \"merchantRef\": \"6682942d5273633e7b8d30c8\",\r\n    \"merchantName\": \"merchant002\",\r\n    \"purchase\": {\r\n        \"currency\": \"INR\",\r\n        \"products\": [\r\n            {\r\n                \"name\": \"test\",\r\n                \"quantity\": 1.0,\r\n                \"price\": 10.0,\r\n                \"discount\": 0,\r\n                \"tax_percent\": \"0.00\"\r\n            }\r\n        ],\r\n        \"total\": 10.0,\r\n        \"language\": \"en\",\r\n        \"notes\": \"\",\r\n        \"debt\": 0,\r\n        \"total_formatted\": 1.0,\r\n        \"request_client_details\": [],\r\n        \"timezone\": \"MIT\",\r\n        \"email_message\": \"\"\r\n    },\r\n    \"payment\": {\r\n        \"is_outgoing\": false,\r\n        \"payment_type\": \"PURCHASE\",\r\n        \"amount\": 10.0,\r\n        \"currency\": \"INR\",\r\n        \"net_amount\": 10.0,\r\n        \"fee_amount\": 0.0,\r\n        \"pending_amount\": 0.0,\r\n        \"pending_unfreeze_on\": null,\r\n        \"description\": \"\",\r\n        \"paid_on\": 1719833645,\r\n        \"remote_paid_on\": 1719833645\r\n    },\r\n    \"issuer_details\": {\r\n        \"website\": \"\",\r\n        \"legal_street_address\": \"\",\r\n        \"legal_country\": \"\",\r\n        \"legal_city\": \"\",\r\n        \"legal_zip_code\": \"\",\r\n        \"bank_accounts\": [\r\n            {}\r\n        ],\r\n        \"legal_name\": \"test6\",\r\n        \"brand_name\": \"test6\",\r\n        \"registration_number\": \"\",\r\n        \"tax_number\": \"\"\r\n    },\r\n    \"transaction_data\": {\r\n        \"payment_method\": \"\",\r\n        \"flow\": \"payform\",\r\n        \"extra\": {\r\n            \"amount\": 10.0,\r\n            \"masked_pan\": \"UPI\"\r\n        },\r\n        \"country\": \"\",\r\n        \"attempts\": [\r\n            {\r\n                \"client_ip\": \"110.235.229.42\",\r\n                \"type\": \"execute\",\r\n                \"payment_method\": \"UPI-QR\",\r\n                \"flow\": \"payform\",\r\n                \"successful\": true,\r\n                \"country\": \"UPI\",\r\n                \"processing_time\": 1719833645,\r\n                \"extra\": {\r\n                    \"amount\": 10.0,\r\n                    \"masked_pan\": \"UPI\"\r\n                }\r\n            }\r\n        ]\r\n    },\r\n    \"status\": \"PAYMENT_IN_PROCESS\",\r\n    \"status_history\": [\r\n        {\r\n            \"status\": \"created\",\r\n            \"timestamp\": 1719833645\r\n        },\r\n        {\r\n            \"status\": \"pending_execute\",\r\n            \"timestamp\": 1719833645\r\n        },\r\n        {\r\n            \"status\": \"payment_in_process\",\r\n            \"timestamp\": 1719833645\r\n        }\r\n    ],\r\n    \"is_test\": false,\r\n    \"brand_id\": \"c4003b2c-22d4-4dc1-ad0c-c6b54f8c9636\",\r\n    \"send_receipt\": false,\r\n    \"is_recurring_token\": false,\r\n    \"skip_capture\": false,\r\n    \"reference_generated\": \"PS10421\",\r\n    \"issued\": \"2024-07-01\",\r\n    \"due\": 1719833645,\r\n    \"refund_upto\": 0,\r\n    \"cc_descriptor\": \"\",\r\n    \"fraudScore\": \"NA\",\r\n    \"trustScore\": \"NA\",\r\n    \"payInDetails\": {\r\n        \"expiration_date\": \"2025-03-27 23:59:59\",\r\n        \"qrCode\": \"iVBORw0KGgoAAAANSUhEUgAAAb0AAAG9AQAAAACpVZXpAAAH7UlEQVR4nO1cQY7qSgw0yiJLjpCbJBdDIhIXg5vkCCyzQPi7qtwkM2/zNcsYpIfeQFcvTNtdLtsx/9trtS/wC/wCv8A/AZ9mdnpevb9bt6zj+TWso3Uen17i33nGkgverotN/orP7FoHeHV/AG1nfnoZ+kfYrcdKv8ei/gEMvljxRkQZ4MVi5Ww2nm9LbBF/xnLYd7YVVu3dZ262hPUvA3+CUsCnDesJ39/PHhidtlg5cRFek9+WtSgwPO595ldGI4dTAohX/8ZpG2Hp8MdiQPnjEL7XIWJdEae6BfvgC0SxCGCx2Q2fvf5x5GMDGckRov7X2+8r4NhAvW6O82QrHBBeuGBHHjSHK7rDtDxtv8jD0YERv8PPwAHcRjogbv43/BF/wuZwytgHO9r4serxgbIg7vvzPNALY1GHzXDrwYJji2JgTsvOkY8PxGnDDYeVsPHcYjWoUtx6jF04cjPsa8PmjxWAroMWUbtbdPPHPuGZsOqdX8SfOJXGu26zagVgLILHraTWvOUDjRuuU4jq4a2xj8y9hLd6HaArFcMtD997gVoHJYCRwa8H2HzgWVxBDkoBxR5lraVHxIpgdWXEcjJKHrmw+S2Z071F8gLA+JSGCkwEbISoOFnJHiNtvSAhgc0RpyKmw/BeBqgUFUcJGIPWAZnjY1VXis+bUMdw93McHph0kXedfA/pBfMx5CKLlJCJ9n3+FEkOD1QSiuUyrSWaQfyuc0eS3UElm+m8ZYDNqrCbkQMgMMGWEcCQhdEB6a1Jsps/VgCGybASWTtOFu1Lz8SlD/lsgheepBXFupaUFQEiC4MXzozaRjYQrnhRAksioORDbx8doAAQkfwM3qzrP4MVI3lwRqeEOEgTgc37eyVg5zxFZNAuboR0HlkY5VZdbszbELtk6SpAk/DV44yBB2H5zFSWgR3KPAkSKIHZT3nt6EA4INgPmKJRim/1L1MljKI8zS0NbSwElG5qrX6DwsQkDQh5Kr91prI3V4jfqHUBYKfKH9jPQPbDCpchTkmop/xzgiYi9dULASm2863TQeuxGYuDYVUzmtFOm3tuxaDjA+Fi0AehAZFB0zOpfxikD4Uo7YOw9SFIBYAqkN4UyRnY4ZnNFWnfVlpX7WeTEI8PBGWepDvLZCDPopBZOQVVgj+CCNwaaaoBxP8p/zDloN5jZI/sQABGeYe7ctftyBUAPpmmozqBpAyZ/ArxmXmqfJTqIZVWbLGJJBWAtCXqN8rCqIN1rqh9N0qIs84dGzU2raMAkPEbJjMWt85atJg1fZXZhm7CURyqDvCpWpejnUci4QrxmWSSVQwqRGwT47qdEFQBOPCWpxeCPBulsl55KiyIOM96hiLWw+sAndSQB+1KqQxnjEBmIC+xb2NNjFnJp95RASjimEViKtAiTWoEM1bf1YHK2vKOPR4fiJuLyrIZuk0hNOP6Z9McsxJk8gsJEm44sYEqQHaghvF4fQk9ch+9MXR3aOdRJA9KsJVKDw9k1FbDE1WyiOkUghiwSQlQycmyz5mCRyWgZxAyFU2dJJvxm59RsgerlmS/XXMFgOzfYU3H1OFuSlaRnq288JyuyL5dhLJPB0IBIBa9mbCrOYxaqkqlqPwhlcU1B89Ud/wnklcABjdCmi4dEcoyo1Nrt2yVsDGrGGpqrgNUqY8siQblQXMeOcZv6Ijr1LpYdjWd4wM9h2yYcanE02gRxY3WmSHSxBKP1wFK4NFVz0i0jZUwO2Viz3PHA7nrfD4+8MlRLCRl4NITs42WxPdZxKGQdpXSah/aWQDo5IcJVB2ZhBrHi0UcmjY7eH/8HAWAraaTxMfSAU1ah9E9L8pAVD6tBGQnt/h1bMFGg3fLMdjUwvaMNfMOzCJtR+7wQPWucKBmZjjnV61DjJtxXkJpiO1qOhWAOV/TYhKcUpM2F91rxqGJVrHYdXcXAPIA5dDsIPXwnUZWOxRpgrMjEzORW8GrAnDO4tbE8QnORrCfBeeOMvSk3h/LLR6FgNtIIyui1OglaTAhYXNYamicufGdIx8eqFz9ZTkMYWy8dA1vqRp4Ir/2WcLINlBQAPgkIWQQz0c8OFvlkl8zA5lzGAeHz9+FgO6ii+y9QCRSowHdTtH9xOZTjWBn6asKUK2VvtBaUuFH+R62oAZkObLfKzM71wHCqhyVaFPpIs/emndV+mLfBmtivv85Dg9kAwajE+K3kg8lpq3YA0dlY48GAM+FgDklq7wDoVtUaVT/e/YdJDdiUcPrAHmeFJhemkBKMunZ/y6nZDeYGMKmzB8eCBshHW1T6VhuqdabzmI+P2Tpm1OWAWoei88uSBV+o9G7eimfN4O0f9e/enyg9PgL5Xk9tqDP9OKmKilbCNU0dxL6Wgr4aOlo/yGOagQ7yeZqwYRnXndlxArAnNHfRvbzXlML5ktJmWdij2rgsxAQVlVJMF2xaUCcGuUH6n9SpX3f9XR8IF7qQIiTlUWcznXf5/CRZfflqIGuaxkgDEVqaOyX4+VmnNvic2SyTCi5VRWfdgVUAF5dUVtj6KrpwL545dMX7TNg/LMaeHygnr7YxNM2JcEvVOLJrISKolk9oPpxW7ep+JJodLJqnkpN9Vs1IFxsarqzpLKHsrUXGaW1+vrFfj3w8+BA+iOHA1omrxbCJ9F67IP2oUK04+QFgC2Sq8U7x5CGTyVsaL3LLjIp9ywC/NPrC/wCv8Av8C/A/wCpreUSrYyOqQAAAABJRU5ErkJggg==\",\r\n    },\r\n    \"refund_availability\": \"NONE\",\r\n    \"refundable_amount\": 0.0,\r\n    \"success_redirect\": \"https://your.success.redirect.com\",\r\n    \"pending_redirect\": \"https://your.pending.redirect.com\",\r\n    \"failure_redirect\": \"https://your.failure.redirect.com\",\r\n    \"success_callback\": \"https://your.success.callback.com\",\r\n    \"failure_callback\": \"https://your.failure.callback.com\"\r\n    \"platform\": \"API\",\r\n    \"created_from_ip\": \"110.235.229.42\",\r\n    \"checkout_url\": \"https://api.paysecure.net/payments/6682942d5273633e7b8d30c8/\"\r\n}\r\n"
```


# Get Status 4

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
async getStatus4(
  purchaseId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success10>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success10`](../../doc/models/success-10.md).

## Example Usage

```ts
const purchaseId = 'purchaseId2';

try {
  const response = await payinApIsApi.getStatus4(purchaseId);

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
        "quantity": 1.0,
        "price": 10.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 10.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "expireInMin": "35",
    "request_client_details": [],
    "timezone": "MIT",
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 10.0,
    "currency": "INR",
    "net_amount": 10.0,
    "fee_amount": 0.0,
    "pending_amount": 0.0,
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
      "amount": 10.0,
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
          "amount": 10.0,
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
    "expiration_date": "2025-03-27 23:59:59",
    "qrCode": "iVBORw0KGgoAAAANSUhEUgAAAb0AAAG9AQAAAACpVZXpAAAH7UlEQVR4nO1cQY7qSgw0yiJLjpCbJBdDIhIXg5vkCCyzQPi7qtwkM2/zNcsYpIfeQFcvTNtdLtsx/9trtS/wC/wCv8A/AZ9mdnpevb9bt6zj+TWso3Uen17i33nGkgverotN/orP7FoHeHV/AG1nfnoZ+kfYrcdKv8ei/gEMvljxRkQZ4MVi5Ww2nm9LbBF/xnLYd7YVVu3dZ262hPUvA3+CUsCnDesJ39/PHhidtlg5cRFek9+WtSgwPO595ldGI4dTAohX/8ZpG2Hp8MdiQPnjEL7XIWJdEae6BfvgC0SxCGCx2Q2fvf5x5GMDGckRov7X2+8r4NhAvW6O82QrHBBeuGBHHjSHK7rDtDxtv8jD0YERv8PPwAHcRjogbv43/BF/wuZwytgHO9r4serxgbIg7vvzPNALY1GHzXDrwYJji2JgTsvOkY8PxGnDDYeVsPHcYjWoUtx6jF04cjPsa8PmjxWAroMWUbtbdPPHPuGZsOqdX8SfOJXGu26zagVgLILHraTWvOUDjRuuU4jq4a2xj8y9hLd6HaArFcMtD997gVoHJYCRwa8H2HzgWVxBDkoBxR5lraVHxIpgdWXEcjJKHrmw+S2Z071F8gLA+JSGCkwEbISoOFnJHiNtvSAhgc0RpyKmw/BeBqgUFUcJGIPWAZnjY1VXis+bUMdw93McHph0kXedfA/pBfMx5CKLlJCJ9n3+FEkOD1QSiuUyrSWaQfyuc0eS3UElm+m8ZYDNqrCbkQMgMMGWEcCQhdEB6a1Jsps/VgCGybASWTtOFu1Lz8SlD/lsgheepBXFupaUFQEiC4MXzozaRjYQrnhRAksioORDbx8doAAQkfwM3qzrP4MVI3lwRqeEOEgTgc37eyVg5zxFZNAuboR0HlkY5VZdbszbELtk6SpAk/DV44yBB2H5zFSWgR3KPAkSKIHZT3nt6EA4INgPmKJRim/1L1MljKI8zS0NbSwElG5qrX6DwsQkDQh5Kr91prI3V4jfqHUBYKfKH9jPQPbDCpchTkmop/xzgiYi9dULASm2863TQeuxGYuDYVUzmtFOm3tuxaDjA+Fi0AehAZFB0zOpfxikD4Uo7YOw9SFIBYAqkN4UyRnY4ZnNFWnfVlpX7WeTEI8PBGWepDvLZCDPopBZOQVVgj+CCNwaaaoBxP8p/zDloN5jZI/sQABGeYe7ctftyBUAPpmmozqBpAyZ/ArxmXmqfJTqIZVWbLGJJBWAtCXqN8rCqIN1rqh9N0qIs84dGzU2raMAkPEbJjMWt85atJg1fZXZhm7CURyqDvCpWpejnUci4QrxmWSSVQwqRGwT47qdEFQBOPCWpxeCPBulsl55KiyIOM96hiLWw+sAndSQB+1KqQxnjEBmIC+xb2NNjFnJp95RASjimEViKtAiTWoEM1bf1YHK2vKOPR4fiJuLyrIZuk0hNOP6Z9McsxJk8gsJEm44sYEqQHaghvF4fQk9ch+9MXR3aOdRJA9KsJVKDw9k1FbDE1WyiOkUghiwSQlQycmyz5mCRyWgZxAyFU2dJJvxm59RsgerlmS/XXMFgOzfYU3H1OFuSlaRnq288JyuyL5dhLJPB0IBIBa9mbCrOYxaqkqlqPwhlcU1B89Ud/wnklcABjdCmi4dEcoyo1Nrt2yVsDGrGGpqrgNUqY8siQblQXMeOcZv6Ijr1LpYdjWd4wM9h2yYcanE02gRxY3WmSHSxBKP1wFK4NFVz0i0jZUwO2Viz3PHA7nrfD4+8MlRLCRl4NITs42WxPdZxKGQdpXSah/aWQDo5IcJVB2ZhBrHi0UcmjY7eH/8HAWAraaTxMfSAU1ah9E9L8pAVD6tBGQnt/h1bMFGg3fLMdjUwvaMNfMOzCJtR+7wQPWucKBmZjjnV61DjJtxXkJpiO1qOhWAOV/TYhKcUpM2F91rxqGJVrHYdXcXAPIA5dDsIPXwnUZWOxRpgrMjEzORW8GrAnDO4tbE8QnORrCfBeeOMvSk3h/LLR6FgNtIIyui1OglaTAhYXNYamicufGdIx8eqFz9ZTkMYWy8dA1vqRp4Ir/2WcLINlBQAPgkIWQQz0c8OFvlkl8zA5lzGAeHz9+FgO6ii+y9QCRSowHdTtH9xOZTjWBn6asKUK2VvtBaUuFH+R62oAZkObLfKzM71wHCqhyVaFPpIs/emndV+mLfBmtivv85Dg9kAwajE+K3kg8lpq3YA0dlY48GAM+FgDklq7wDoVtUaVT/e/YdJDdiUcPrAHmeFJhemkBKMunZ/y6nZDeYGMKmzB8eCBshHW1T6VhuqdabzmI+P2Tpm1OWAWoei88uSBV+o9G7eimfN4O0f9e/enyg9PgL5Xk9tqDP9OKmKilbCNU0dxL6Wgr4aOlo/yGOagQ7yeZqwYRnXndlxArAnNHfRvbzXlML5ktJmWdij2rgsxAQVlVJMF2xaUCcGuUH6n9SpX3f9XR8IF7qQIiTlUWcznXf5/CRZfflqIGuaxkgDEVqaOyX4+VmnNvic2SyTCi5VRWfdgVUAF5dUVtj6KrpwL545dMX7TNg/LMaeHygnr7YxNM2JcEvVOLJrISKolk9oPpxW7ep+JJodLJqnkpN9Vs1IFxsarqzpLKHsrUXGaW1+vrFfj3w8+BA+iOHA1omrxbCJ9F67IP2oUK04+QFgC2Sq8U7x5CGTyVsaL3LLjIp9ywC/NPrC/wCv8Av8C/A/wCpreUSrYyOqQAAAABJRU5ErkJggg=="
  },
  "refund_availability": "NONE",
  "refundable_amount": 10.0,
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


# Payin AP Is

### 1\. Request Payload Structure

Supply a JSON payload with these top‐level objects:

- `client` (customer details)

- `purchase` (order details)

- `paymentMethod` (string, must be `"SPEI"`)

- `extraParam` (optional, leave `{}` if unused)

- `status` (set to `"created"`)

- `brand_id` (your merchant/brand UUID)

- Redirect & callback URLs

---


### 2\. Displaying SPEI Instructions to End User

Once you parse `payInDetails` from the response:

1. **Show CLABE, Beneficiary & Amount**

2. **Display Expiration**

3. **Show Redirect Path (Optional)**
   
   - If you’re using the hosted `checkout_url`, simply redirect customers to it and let Paysecure handle the UI.

---


### 3\. Webhook Handling & Status Transitions

1. **Configure Webhooks**
   
   - In Paysecure’s Dashboard, set your `success_callback` and `failure_callback` URLs (one for each event type).

2. **Listen for These Events**:
   
   - `payment.paid` – Banco de México has settled the transfer.
   
   - `payment.error` – CLABE/amount mismatch or network error.
   
   - `payment.expired` – Customer did not pay before `expireInMin`.

3. **Update Order Status**:
   
   - On `payment.paid`: mark as paid, trigger fulfillment, send confirmation.
   
   - On `payment.error`: alert customer, allow retry or alternative payment.
   
   - On `payment.expired`: cancel order.

:information_source: **Note** This endpoint does not require authentication.

```ts
async payinApIs(
  body: PayinApIsRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success11>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PayinApIsRequest`](../../doc/models/payin-ap-is-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success11`](../../doc/models/success-11.md).

## Example Usage

```ts
const body: PayinApIsRequest = {
  client: {
    email: 'ashishm.21190@gmail.com',
    streetAddress: 'test test',
    city: '123',
    fullName: 'Test test',
    zipCode: '234567',
    country: 'MX',
    stateCode: 'ca',
    phone: '9999999999',
  },
  purchase: {
    currency: 'MXN',
    products: [
      {
        name: 'dk',
        price: '100',
      }
    ],
  },
  paymentMethod: 'SPEI',
  brandId: '{{merchant_brand_id}}',
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
};

try {
  const response = await payinApIsApi.payinApIs(body);

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
  "purchaseId": "683d768a22ae19559d740836",
  "client": {
    "customerId": "NA",
    "email": "ashishm.21190@gmail.com",
    "phone": "9999999999",
    "full_name": "Test test",
    "date_of_birth": "1970-07-10",
    "street_address": "test test",
    "country": "MX",
    "city": "123",
    "zip_code": "234567",
    "cc": [],
    "bcc": [],
    "stateCode": "ca"
  },
  "updated_on": 1748858506,
  "type": "purchase",
  "paymentMethod": "SPEI",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "redirectType": "GET",
  "force_recurring": false,
  "created_on": 1748858506,
  "extraParam": {},
  "merchantRef": "683d768a22ae19559d740836",
  "merchantName": "arunsinghal",
  "purchase": {
    "currency": "MXN",
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
    "expireInMin": "4320",
    "taxAmount": 0,
    "taxPercent": 0,
    "request_client_details": [],
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 100,
    "currency": "MXN",
    "net_amount": 100,
    "fee_amount": 0,
    "pending_amount": 0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1748858506,
    "remote_paid_on": 1748858506
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
      "amount": 100,
      "masked_pan": "SPEI"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "103.59.75.242, 162.158.22.197, 130.176.183.5",
        "type": "execute",
        "payment_method": "SPEI",
        "flow": "payform",
        "successful": true,
        "country": "SPEI",
        "processing_time": 1748858506,
        "extra": {
          "amount": 100,
          "masked_pan": "SPEI"
        }
      }
    ]
  },
  "status": "PAYMENT_IN_PROCESS",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1748858506
    },
    {
      "status": "pending_execute",
      "timestamp": 1748858506
    },
    {
      "status": "payment_in_process",
      "timestamp": 1748858506
    }
  ],
  "is_test": false,
  "brand_id": "{{your_brand_id}}",
  "is_recurring_token": false,
  "reference_generated": "PS786",
  "issued": "2025-06-02",
  "due": 1748858506,
  "refund_upto": 1749891706,
  "cc_descriptor": "",
  "fraudScore": "0",
  "trustScore": "2",
  "payInDetails": {
    "clabe": "710969000049618169",
    "beneficiary": "CHOICEPAY LTD.",
    "amount": "100.00"
  },
  "paidOn": 0,
  "refund_availability": "NONE",
  "refundable_amount": 100,
  "success_redirect": "https://your.success.redirect.com",
  "failure_redirect": "https://your.failure.redirect.com",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.com",
  "failure_callback": "https://your.failure.callback.com",
  "platform": "API",
  "created_from_ip": "103.59.75.242, 162.158.22.197, 130.176.183.5",
  "checkout_url": "https://api.choicepay.ca/payments/683d768a22ae19559d740836/",
  "payoutProcess": false
}
```


# Purchases 5

To Initiate a payment, the very first call to make is `/purchases` with the required data in the request body.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.email | An Identifier for a user, should be a valid email. |
| client.city | City of the user. |
| client.country | ISO-3166 Country Code. It must be upper case. |
| client.stateCode | ISO-3166-2 State Code. Must be in upper case. |
| client.street_address | street address of the user. |
| client.zip_code | zip code of the user. |
| client.phone | Phone number of the user. Country code is mandatory.  <br>Example: +234999999999 |
| client.full_name | Full name of the user. Minimum 2 words with atleast 1 character in each word. |
| purchase.currency | ISO 4217 code for currency you want to send the transaction in.  <br>eg. This should be 'TZS' for Tanzania  <br>CDF for Congo. |
| purchase.products.name |  |
| purchase.products.price | Amount in decimal upto 2 places. |
| brand_id | Obtain from Dashboard section of your merchant account login. |
| success_redirect | URL to send the user if the transactions is successful |
| pending_redirect | URL to send the user if the transactions is in progress |
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
async purchases5(
  body: PurchasesRequest5,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success13>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchasesRequest5`](../../doc/models/purchases-request-5.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success13`](../../doc/models/success-13.md).

## Example Usage

```ts
const body: PurchasesRequest5 = {
  client: {
    email: 'akshaya@gmail.com',
    streetAddress: '10 New Burlington StreetApt. 214',
    city: 'London',
    fullName: 'akshaya singhal',
    zipCode: 'W1S 3BE',
    country: 'CD',
    dateOfBirth: '1994-31-04',
    stateCode: 'RJ',
    phone: '+243999999999',
  },
  purchase: {
    currency: 'CDF',
    products: [
      {
        name: 'Test Product',
        price: '100',
      }
    ],
  },
  paymentMethod: 'MOBILEMONEY',
  brandId: 'your-brand-id',
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
};

try {
  const response = await payinApIsApi.purchases5(body);

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
  "purchaseId": "69ec68f9f76f0f58bd700058",
  "client": {
    "customerId": "NA",
    "email": "agarapex@gmail.com",
    "phone": "243995980380",
    "full_name": "Rahul Agarwal",
    "date_of_birth": "1994-31-04",
    "street_address": "10 New Burlington StreetApt. 214",
    "country": "CD",
    "city": "Jaipur",
    "zip_code": "W1S 3BE",
    "cc": [],
    "bcc": [],
    "stateCode": "RJ"
  },
  "updated_on": 1777101049,
  "type": "purchase",
  "paymentMethod": "MOBILEMONEY",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "errorCode": "NA",
  "force_recurring": false,
  "created_on": 1777101049,
  "merchantRef": "69ec68f9f76f0f58bd700058",
  "purchase": {
    "currency": "CDF",
    "products": [
      {
        "name": "gaming cards",
        "quantity": 1.0,
        "price": 1000.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 1000.0,
    "requestAmount": 1000.0,
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
    "legal_name": "Testing",
    "brand_name": "Testing",
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
      "timestamp": 1777101049
    }
  ],
  "is_test": false,
  "brand_id": "59c5ed48-caf9-464a-ba54-26e1e02bc1bc",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS1711",
  "issued": "2026-04-25",
  "due": 1777101049,
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
  "success_redirect": "https://google.com/",
  "failure_redirect": "https://paysecure.net",
  "pending_redirect": "https://facebook.com",
  "cancel_redirect": "",
  "success_callback": "https://staging.paysecure.net/merchant",
  "failure_callback": "https://staging.paysecure.net/merchant",
  "platform": "API",
  "created_from_ip": "2406:b400:75:584c:8889:bfe5:9552:8720",
  "checkout_url": "https://api.choicepay.ca/payments/5f95c39387eefc684560013794f41455/",
  "payoutProcess": false
}
```


# Purchases 6

To Initiate a payment, the very first call to make is `/purchases` with the required data in the request body.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.email | An Identifier for a user |
| client.city | An Identifier for a user |
| client.country | ISO-3166 Country Code. It must be upper case.  <br>This should be "CA" for Interac |
| client.stateCode | Example “AL”, “XZ”.. Must be in upper case. |
| client.street_address |  |
| client.zip_code |  |
| client.phone |  |
| client.full_name |  |
| purchase.currency | ISO 4217 code for currency you want to send the transaction in.  <br>This should be 'CAD' for Interac |
| purchase.products.name | name of the product or service |
| purchase.products.price | Price in decimal format.  <br>example 1:  <br>EUR 5 , should be sent as 5.00  <br>  <br>example 2:  <br>USD 10 and 37 cents , should be sent as 10.37 |
| brand_id | Obtain from Dashboard section of your merchant account login. |
| extraParam.IsCryptoPurchase | for paymint, send "Yes" |
| success_redirect | URL to send the user if the transactions is successful |
| pending_redirect | URL to send the user if the transactions is in progress |
| failure_redirect | URL to send the user if the transactions is UNSUCCESSFUL |

## Optional Parameters

### expireInMin

The `purchase.expireInMin`, when passed in the PayIn request, sets the time window within which a customer should make the Interac payment through their bank's app. If a customer doesn't complete the payment within the configured time window, the status of the payment will be marked as 'EXPIRED' in Paysecure.

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
async purchases6(
  body: PurchasesRequest8,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PurchaseSuccess>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchasesRequest8`](../../doc/models/purchases-request-8.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchaseSuccess`](../../doc/models/purchase-success.md).

## Example Usage

```ts
const body: PurchasesRequest8 = {
  client: {
    email: 'seo2009@test.com',
    streetAddress: '10 New Burlington Street Apt. 214',
    city: 'London',
    fullName: 'Test test',
    zipCode: 'W1S 3BE',
    country: 'CA',
    stateCode: 'QLD',
    phone: '+447755564318',
  },
  purchase: {
    currency: 'CAD',
    expireInMin: '80',
    products: [
      {
        name: 'test ',
        price: 100,
      }
    ],
  },
  extraParam: {
    isCryptoPurchase: 'yes',
  },
  paymentMethod: '',
  brandId: 'f6aff7d7-bb40-4857-bc84-9b4c8310b043',
  successRedirect: 'https://your.redirect.url/getResponse.jsp?success=true',
  pendingRedirect: 'https://your.redirect.url/getResponse.jsp?success=true',
  failureRedirect: 'https://your.redirect.url/getResponse.jsp?success=false',
  successCallback: 'https://your.success.callback.url',
  failureCallback: 'https://your.success.failure.url',
};

try {
  const response = await payinApIsApi.purchases6(body);

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
  "purchaseId": "67efd0ff97be603f97a3a697",
  "client": {
    "customerId": "NA",
    "email": "ashishm.21190@gmail.com",
    "phone": "+447755564318",
    "full_name": "Test test",
    "date_of_birth": "1970-07-10",
    "street_address": "10 New Burlington Street Apt. 214",
    "country": "CA",
    "city": "London",
    "zip_code": "W1S 3BE",
    "cc": [],
    "bcc": [],
    "gender": "MALE",
    "avatarUrl": "https://res.cloudinary.com/w22/image/upload/v1663783641/photos/currencies/ngn.png",
    "stateCode": "QLD"
  },
  "updated_on": 1743769856,
  "type": "purchase",
  "paymentMethod": "INTERAC-ETRANSFER",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "redirectType": "GET",
  "force_recurring": false,
  "created_on": 1743769855,
  "merchantRef": "67efd0ff97be603f97a3a697",
  "merchantName": "arunsinghal",
  "purchase": {
    "currency": "CAD",
    "products": [
      {
        "name": "test",
        "quantity": 1.0,
        "price": 1.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 1.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "expireInMin": "43200",
    "taxAmount": 0.0,
    "taxPercent": 0.0,
    "request_client_details": [],
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 1.0,
    "currency": "CAD",
    "net_amount": 1.0,
    "fee_amount": 0.0,
    "pending_amount": 0.0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1743769855,
    "remote_paid_on": 1743769855
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
      "amount": 1.0,
      "masked_pan": "INTERAC-ETRANSFER"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "103.59.75.41, 162.158.88.44, 130.176.93.146",
        "type": "execute",
        "payment_method": "INTERAC-ETRANSFER",
        "flow": "payform",
        "successful": true,
        "country": "INTERAC-ETRANSFER",
        "processing_time": 1743769855,
        "extra": {
          "amount": 1.0,
          "masked_pan": "INTERAC-ETRANSFER"
        }
      }
    ]
  },
  "status": "PAYMENT_IN_PROCESS",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1743769855
    },
    {
      "status": "pending_execute",
      "timestamp": 1743769855
    },
    {
      "status": "payment_in_process",
      "timestamp": 1743769856
    },
    {
      "status": "viewed",
      "timestamp": 1744026697
    }
  ],
  "viewedOn": 1744026697,
  "is_test": false,
  "brand_id": "30f7ce6e-3b7e-46a2-9b50-484fc55be689",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS620",
  "issued": "2025-04-04",
  "due": 1743769855,
  "refund_upto": 0,
  "cc_descriptor": "Africhange Technologies",
  "fraudScore": "NA",
  "trustScore": "NA",
  "payInDetails": {
    "name": "INTERAC",
    "emailAddress": "transfer@ieft.ca",
    "secretQA": "66a8c78af1fc2f768304bce4",
    "secretAnswer": "ps8766a8af"
  },
  "paidOn": 0,
  "receivedAmt": 0.0,
  "refund_availability": "NONE",
  "refundable_amount": 0.0,
  "success_redirect": "https://your.redirect.url/getResponse.jsp?success=true",
  "failure_redirect": "https://your.redirect.url/getResponse.jsp?success=false",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.url",
  "failure_callback": "https://your.success.failure.url",
  "platform": "API",
  "created_from_ip": "103.59.75.41, 162.158.88.44, 130.176.93.146",
  "checkout_url": "https://api.choicepay.ca/payments/67efd0ff97be603f97a3a697/",
  "payoutProcess": false
}
```


# Get Status 5

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
async getStatus5(
  purchaseId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PurchasesSuccess1>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PurchasesSuccess1`](../../doc/models/purchases-success-1.md).

## Example Usage

```ts
const purchaseId = 'purchaseId2';

try {
  const response = await payinApIsApi.getStatus5(purchaseId);

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
  "purchaseId": "6790e75fa46a5a5bb0b00e55",
  "client": {
    "customerId": "NA",
    "email": "ashishm.21190@gmail.com",
    "phone": "+14377717874",
    "full_name": "Test test",
    "date_of_birth": "1970-07-10",
    "street_address": "10 New Burlington Street Apt. 214",
    "country": "CA",
    "city": "London",
    "zip_code": "W1S 3BE",
    "cc": [],
    "bcc": [],
    "gender": "MALE",
    "stateCode": "QLD"
  },
  "updated_on": 1737549752,
  "type": "purchase",
  "paymentMethod": "INTERAC-ETRANSFER",
  "amountUnit": "MAJOR",
  "errorMsg": "Transaction succeeded-APPROVED",
  "redirectType": "GET",
  "force_recurring": false,
  "created_on": 1737549663,
  "merchantRef": "6790e75fa46a5a5bb0b00e55",
  "merchantName": "arunsinghal",
  "purchase": {
    "currency": "CAD",
    "products": [
      {
        "name": "test",
        "quantity": 1,
        "price": 1,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 2,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1,
    "expireInMin": "43200",
    "request_client_details": [],
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 1,
    "currency": "CAD",
    "net_amount": 1,
    "fee_amount": 0,
    "pending_amount": 0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1737549663,
    "remote_paid_on": 1737549663
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
      "amount": 1,
      "masked_pan": "INTERAC-ETRANSFER"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "103.59.75.42, 172.71.186.102, 130.176.183.14",
        "type": "execute",
        "payment_method": "INTERAC-ETRANSFER",
        "flow": "payform",
        "successful": true,
        "country": "INTERAC",
        "processing_time": 1737549663,
        "extra": {
          "amount": 1,
          "masked_pan": "INTERAC-ETRANSFER"
        }
      }
    ]
  },
  "status": "PAID",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1737549663
    },
    {
      "status": "pending_execute",
      "timestamp": 1737549663
    },
    {
      "status": "payment_in_process",
      "timestamp": 1737549664
    },
    {
      "status": "paid 2.0",
      "timestamp": 1737549752
    },
    {
      "status": "viewed",
      "timestamp": 1737549750
    }
  ],
  "viewedOn": 1738749942,
  "is_test": false,
  "brand_id": "30f7ce6e-3b7e-46a2-9b50-484fc55be689",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS376",
  "issued": "2025-01-22",
  "due": 1737549663,
  "refund_upto": 0,
  "cc_descriptor": "Africhange Technologies",
  "fraudScore": "NA",
  "trustScore": "NA",
  "payInDetails": {
    "name": "INTERAC",
    "emailAddress": "deposit@ieft.ca",
    "secretQA": "66a8c78af1fc2f768304bce4",
    "secretAnswer": "ps8766a8af"
  },
  "paidOn": 1737549752,
  "receivedAmt": 2,
  "refund_availability": "NONE",
  "refundable_amount": 0,
  "success_redirect": "https://your.redirect.url/getResponse.jsp?success=true",
  "failure_redirect": "https://your.redirect.url/getResponse.jsp?success=false",
  "cancel_redirect": "",
  "success_callback": "https://webhook.site/83df9776-3590-4e25-9222-870e931ac868",
  "failure_callback": "https://webhook.site/83df9776-3590-4e25-9222-870e931ac868",
  "platform": "API",
  "created_from_ip": "103.59.75.42, 172.71.186.102, 130.176.183.14",
  "checkout_url": "https://api.choicepay.ca/payments/6790e75fa46a5a5bb0b00e55/",
  "payoutProcess": false
}
```


# Purchases 7

The API endpoint [/v1/purchases](https://api.paysecure.net/api/v1/purchases) is a POST request used to create a new purchase. The request body should contain the client information including email, address, and phone, the purchase details such as currency and products, the payment method, and various callback and redirect URLs.

**Final Steps for Payin APIs Integration**

1. **Set Up Authentication & Headers**
   
   - **Endpoint:** POST >
   
   - **Headers (mandatory):**
     
     - Authorization: Bearer {LIVE_API_KEY}
     
     - Content-Type: application/json

2. **Construct the Request Payload**
   
   - Build a JSON body with:
     
     - client object (KYC/AML fields):
       
       - email
       
       - country (ISO-2 code)
       
       - city
       
       - stateCode
       
       - street_address
       
       - zip_code
       
       - phone
     
     - purchase object:
       
       - currency
       
       - products array (≥1 item with name and price)
     
     - **Top-level fields:**
       
       - paymentMethod (e.g., "NEOSURF")
       
       - brand_id (your Brand UUID)
       
       - success_redirect (HTTPS URL after success)
       
       - failure_redirect (HTTPS URL after failure)

3. **Invoke the Payin APIs**
   
   - Send the JSON payload to [https://api.paysecure.net/v1/purchases](https://api.paysecure.net/v1/purchases)
   
   - Expect 200 OK with a response containing:
     
     - purchaseId
     
     - status = PENDING
     
     - checkout_url

4. **Extract Key References**
   
   - purchaseId (e.g., 68394314d3c4ef68d6cbb58c): for tracking/reconciliation.
   
   - checkout_url (e.g., [https://api.paysecure.net/payments/68394314d3c4ef68d6cbb58c/](https://api.paysecure.net/payments/68394314d3c4ef68d6cbb58c/)): redirect here so the customer can complete voucher entry.
   
   - Redirect Customer `window.location.href = response.checkout_url;` Customer enters their 10-digit Neosurf voucher on redirected page.

5. **Listen for Webhook Notifications**
   
   - Ensure your endpoint handles:
     
     - purchase.paid
     
     - purchase.error
     
     - purchase.cancelled
   
   - Each payload will include purchaseId, status, amount, currency, etc.

### Mandatory Parameters

| Field | Type | Description |
| --- | --- | --- |
| **Authorization** | string | `Bearer {API_KEY}` (replace with your live or staging API key). |
| **Content-Type** | string | Must be `application/json`. |
| **client.email** | string | Customer’s email (e.g., `example22@paysecure.net`). |
| **client.country** | string | ISO‐3166 Alpha-2 code (e.g., `IN`). |
| **client.city** | string | City name or code (e.g., `123`). |
| **client.stateCode** | string | State or province code (two letters where possible, e.g., `ca`). |
| **client.street_address** | string | Street address line (e.g., `test test`). |
| **client.zip_code** | string | Postal/ZIP code (e.g., `234567`). |
| **client.phone** | string | Customer’s phone number (E.164 recommended, e.g., `9999999999`). |
| **purchase.currency** | string | Currency code (e.g., `AUD`). |
| **purchase.products** | array | Must contain at least one object with `name` and `price`. |
| └─ **products.name** | string | Product name or SKU (e.g., `dk`). |
| └─ **products.price** | string | Unit price in major currency units (e.g., `"1"` = 1.00 AUD). |
| **paymentMethod** | string | Payment rail code (e.g., `NEOSURF`). |
| **brand_id** | string | Live or staging Brand UUID (e.g., `c4003b2c-22d4-4dc1-ad0c-c6b54f8c9636`). |
| **success_redirect** | string | HTTPS URL to redirect after successful payment (e.g., `https://your.success.redirect.com`). |
| **failure_redirect** | string | HTTPS URL to redirect after failed payment (e.g., `https://your.failure.redirect.com`). |

:information_source: **Note** This endpoint does not require authentication.

```ts
async purchases7(
  body: PurchasesRequest9,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success16>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchasesRequest9`](../../doc/models/purchases-request-9.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success16`](../../doc/models/success-16.md).

## Example Usage

```ts
const body: PurchasesRequest9 = {
  client: {
    email: 'example22@paysecure.net',
    country: 'IN',
    city: '123',
    stateCode: 'ca',
    streetAddress: 'test test',
    zipCode: '234567',
    phone: '9999999999',
  },
  purchase: {
    currency: 'AUD',
    products: [
      {
        name: 'dk',
        price: '1',
      }
    ],
  },
  paymentMethod: 'NEOSURF',
  brandId: '{{your_brand_id_}}',
  sendReceipt: '',
  skipCapture: '',
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
};

try {
  const response = await payinApIsApi.purchases7(body);

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
  "purchaseId": "683d6bab12b471481d4f66cf",
  "client": {
    "customerId": "NA",
    "email": "example22@paysecure.net",
    "phone": "9999999999",
    "date_of_birth": "1800-01-01",
    "street_address": "test test",
    "country": "IN",
    "city": "123",
    "zip_code": "234567",
    "cc": [],
    "bcc": [],
    "stateCode": "ca"
  },
  "updated_on": 1748855724,
  "type": "purchase",
  "paymentMethod": "NEOSURF",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "redirectType": "GET",
  "force_recurring": false,
  "created_on": 1748855723,
  "merchantRef": "683d6bab12b471481d4f66cf",
  "merchantName": "arunsinghal",
  "purchase": {
    "currency": "AUD",
    "products": [
      {
        "name": "dk",
        "quantity": 1,
        "price": 1,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 1,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1,
    "taxAmount": 0,
    "taxPercent": 0,
    "request_client_details": [],
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 1,
    "currency": "AUD",
    "net_amount": 1,
    "fee_amount": 0,
    "pending_amount": 0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1748855723,
    "remote_paid_on": 1748855723
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
      "amount": 1,
      "masked_pan": "NEOSURF"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "103.59.75.242, 162.158.23.126, 130.176.183.12",
        "type": "execute",
        "payment_method": "NEOSURF",
        "flow": "payform",
        "successful": true,
        "country": "NEOSURF",
        "processing_time": 1748855723,
        "extra": {
          "amount": 1,
          "masked_pan": "NEOSURF"
        }
      }
    ]
  },
  "status": "PAYMENT_IN_PROCESS",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1748855723
    },
    {
      "status": "pending_execute",
      "timestamp": 1748855723
    },
    {
      "status": "payment_in_process",
      "timestamp": 1748855724
    }
  ],
  "is_test": false,
  "brand_id": "30f7ce6e-3b7e-46a2-9b50-484fc55be689",
  "is_recurring_token": false,
  "reference_generated": "PS784",
  "issued": "2025-06-02",
  "due": 1748855723,
  "refund_upto": 1749024924,
  "cc_descriptor": "",
  "fraudScore": "0",
  "trustScore": "0",
  "paidOn": 0,
  "refund_availability": "NONE",
  "refundable_amount": 1,
  "success_redirect": "https://your.success.redirect.com",
  "failure_redirect": "https://your.failure.redirect.com",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.com",
  "failure_callback": "https://your.failure.callback.com",
  "platform": "API",
  "created_from_ip": "103.59.75.242, 162.158.23.126, 130.176.183.12",
  "checkout_url": "https://api.choicepay.ca/payments/683d6bab12b471481d4f66cf/",
  "payoutProcess": false
}
```


# Purchases 9

### Purchase API Endpoint

This endpoint allows you to create a new purchase transaction. It processes the purchase details, including client information, product details, and payment method, and returns the result of the transaction.

#### Request Format

- **Method**: POST

- **URL**: `https://api.paysecure.net/api/v1/purchases`

- **Request Body**: The request should be in JSON format and must include the following structure:

#### Response Structure

The response will contain the result of the purchase transaction. The structure of the response may include:

- **status**: Indicates the success or failure of the transaction.

- **message**: A descriptive message regarding the transaction status.

- **transaction_id**: Unique identifier for the transaction (if successful).

- **redirect_url**: URL to redirect the user based on the transaction result.

Make sure to handle the response appropriately based on the status returned.

:information_source: **Note** This endpoint does not require authentication.

```ts
async purchases9(
  body: PurchasesRequest3,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success17>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchasesRequest3`](../../doc/models/purchases-request-3.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success17`](../../doc/models/success-17.md).

## Example Usage

```ts
const body: PurchasesRequest3 = {
  client: {
    email: 'seo2009@test.com',
    streetAddress: '10 New Burlington Street Apt. 214',
    city: 'Sydney',
    fullName: 'Test test',
    zipCode: 'W1S 3BE',
    country: 'AU',
    stateCode: 'QLD',
    phone: '+447755564318',
  },
  purchase: {
    currency: 'AUD',
    products: [
      {
        name: 'test',
        price: 100,
      }
    ],
  },
  paymentMethod: 'PAYID',
  brandId: 'f6aff7d7-bb40-4857-bc84-9b4c8310b043',
  successRedirect: '<https://your.redirect.url/getResponse.jsp?success=true>',
  pendingRedirect: '<https://your.redirect.url/getResponse.jsp?success=true>',
  failureRedirect: '<https://your.redirect.url/getResponse.jsp?success=false>',
  successCallback: '<https://your.success.callback.url>',
  failureCallback: '<https://your>..failure.callback.url',
};

try {
  const response = await payinApIsApi.purchases9(body);

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
    "country": "AU",
    "city": "123",
    "zip_code": "234567",
    "cc": [],
    "bcc": [],
    "stateCode": "ca"
  },
  "updated_on": 1749294123,
  "type": "purchase",
  "paymentMethod": "PAYID",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "redirectType": "POST",
  "force_recurring": false,
  "created_on": 1749294123,
  "merchantRef": "68441c2a7559cf659fd7e835",
  "merchantName": "Merchant002",
  "purchase": {
    "currency": "AUD",
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
  "success_redirect": "<https://your.redirect.url/getResponse.jsp?success=true>",
  "failure_redirect": "<https://your.redirect.url/getResponse.jsp?success=false>",
  "cancel_redirect": "",
  "success_callback": "<https://webhook.site/ec813a7a-4dd1-4aa3-99f3-f01637ab224c>",
  "failure_callback": "<https://webhook.site/ec813a7a-4dd1-4aa3-99f3-f01637ab224c>",
  "platform": "API",
  "created_from_ip": "183.83.54.51",
  "checkout_url": "<https://staging.paysecure.net/payments/68441c2a7559cf659fd7e835/>",
  "payoutProcess": false
}
```


# Purchases 8

To Initiate a payment, the very first call to make is `/purchases` with the required data in the request body.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

### 💡 Key Fields Explained

| Field | Description |
| --- | --- |
| `paymentMethod` | Always use `"CRYPTO-BRIDGE"` to trigger this payment method |
| `currency` | The fiat currency for the order (e.g., USD, EUR). You will be paid in crypto but this defines how much the customer will pay |
| `products` | One or more items being sold, with name and price |
| `extraParam.clientFee` | Optional: A custom fee you (the merchant) want to charge — shown to the user at checkout |
| `extraParam.toAddress` | Optional.  <br>Merchant can provide the list of wallet addresses, where they want to collect the deposit from the user. Can pass multiple addresses. |
| `extraParam.toAddress.symbol` | The symbol of the digital asset.  <br>Example: ETH, USDC etc.  <br>  <br>Possible Values:  <br>AAVE, ADA, APE, APT, ARB, AVAX, BLAST, BLUR, BNB, BTC, BUSD, CAKE, CASH, CRO, DAI, DEXE, DEVNETSOL, DOGE, ENA, ETH, EURC, FARTCOIN, FDUSD, FORM, FTM, GRT, HYPE, IMX, INJ, LDO, LEO, LINK, LTC, MANA, MATIC, MKR, MNT, MON, OP, PAXG, PENGU, POL, PYUSD, QNT, RLUSD, RNDR, S, SAND, SEPOLIAETH, SHIB, SNX, SOL, SUI, TON, TRUMP, TRX, TUSD, UNI, USD1, USD₮0, USDC, USDD, USDG, USDH, USDP, USDT, VIRTUAL, WAVAX, WBNB, WBTC, WETH, WHYPE, WIF, WMATIC, WMON, XLM, XRP |
| `extraParam.toAddress.networkName` | The network of the token.  <br>Example: ETHEREUM, POLYGON etc.  <br>  <br>Possible values:  <br>ETHEREUM, POLYGON, BSC, ARBITRUM, OPTIMISM, BASE, AVALANCHEC, BLAST, HYPEREVM, SOLANA, BITCOIN, TRON, LITECOIN, DOGECOIN, RIPPLE, APTOS, CARDANO, STELLAR, SUI, TON, SONIC, INJECTIVE, AVALANCHEX |
| `extraParam.toAddress.address` | The address to send the asset to. |
| `success_redirect` / `success_redirect` / `failure_redirect` | Where the user should land after completing or canceling the payment or if the transaction is in pending state. |
| `success_callback` / `failure_callback` | Your backend URL to receive transaction status via webhook. |
| `client` | Customer billing info |

:information_source: **Note** This endpoint does not require authentication.

```ts
async purchases8(
  body: PurchasesRequest11,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Purchases1>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchasesRequest11`](../../doc/models/purchases-request-11.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Purchases1`](../../doc/models/purchases-1.md).

## Example Usage

```ts
const body: PurchasesRequest11 = {
  client: {
    email: 'gaurav@gmail.com',
    streetAddress: 'test test',
    city: '123',
    fullName: 'Gaurav Test',
    zipCode: '234567',
    country: 'US',
    stateCode: 'NYC',
    phone: '9999999999',
  },
  purchase: {
    currency: 'USD',
    products: [
      {
        name: 'product name',
        price: 5.86,
      }
    ],
  },
  paymentMethod: 'CRYPTO-BRIDGE',
  brandId: 'cec67fe3-a01d-4d0d-b100-9fafb200fe15',
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  extraParam: {
    clientFee: 0.1,
    toAddress: [
      {
        symbol: 'ETH',
        networkName: 'ETHEREUM',
        address: '0xc4db7bBB898B98D15be823454d1dff6C308BC9A4',
      },
      {
        symbol: 'USDC',
        networkName: 'POLYGON',
        address: '0xc4cs7bBB898B89D15be823445d1dff6C380BC9D3',
      }
    ],
  },
};

try {
  const response = await payinApIsApi.purchases8(body);

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
  "purchaseId": "6874ce9402f0f25ed8fc66a7",
  "client": {
    "customerId": "NA",
    "email": "gaurav@gmail.com",
    "phone": "9999999999",
    "full_name": "Test test",
    "date_of_birth": "1800-01-01",
    "street_address": "test test",
    "country": "US",
    "city": "123",
    "zip_code": "234567",
    "cc": [],
    "bcc": [],
    "tax_number": "39933551809",
    "stateCode": "NYC"
  },
  "updated_on": 1752485524,
  "type": "purchase",
  "paymentMethod": "CRYPTO-BRIDGE",
  "amountUnit": "MAJOR",
  "errorMsg": "",
  "redirectType": "GET",
  "force_recurring": false,
  "created_on": 1752485524,
  "extraParam": {
    "clientFee": 0.1,
    "toAddress": [
      {
        "symbol": "ETH",
        "network": "ETHEREUM",
        "address": "0xc4db7bBB898B98D15be823454d1dff6C308BC9A4"
      },
      {
        "symbol": "USDC",
        "network": "POLYGON",
        "address": "0xc4cs7bBB898B89D15be823445d1dff6C380BC9D3"
      }
    ]
  },
  "merchantRef": "6874ce9402f0f25ed8fc66a7",
  "merchantName": "test",
  "purchase": {
    "currency": "USD",
    "products": [
      {
        "name": "product name",
        "quantity": 1,
        "price": 5.86,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 5.86,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1,
    "taxAmount": 0,
    "taxPercent": 0,
    "request_client_details": [],
    "timezone": "Asia/Hong_Kong",
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 5.86,
    "currency": "USD",
    "net_amount": 5.86,
    "fee_amount": 0,
    "pending_amount": 0,
    "pending_unfreeze_on": null,
    "description": "",
    "paid_on": 1752485524,
    "remote_paid_on": 1752485524
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
    "legal_name": "iUnicharge",
    "brand_name": "iUnicharge",
    "registration_number": "",
    "tax_number": ""
  },
  "transaction_data": {
    "payment_method": "",
    "flow": "payform",
    "extra": {
      "amount": 5.86,
      "masked_pan": "CRYPTO-BRIDGE"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "103.59.75.157, 172.69.203.75, 18.68.12.102",
        "type": "execute",
        "payment_method": "CRYPTO-BRIDGE",
        "flow": "payform",
        "successful": true,
        "country": "CRYPTO-BRIDGE",
        "processing_time": 1752485524,
        "extra": {
          "amount": 5.86,
          "masked_pan": "CRYPTO-BRIDGE"
        }
      }
    ]
  },
  "status": "PAYMENT_IN_PROCESS",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1752485524
    },
    {
      "status": "pending_execute",
      "timestamp": 1752485524
    },
    {
      "status": "payment_in_process",
      "timestamp": 1752485524
    }
  ],
  "is_test": false,
  "brand_id": "cec67fe3-a01d-4d0d-b100-9fafb200fe15",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS1682",
  "issued": "2025-07-14",
  "due": 1752485524,
  "refund_upto": 0,
  "cc_descriptor": "",
  "fraudScore": "100",
  "trustScore": "2",
  "paidOn": 0,
  "refund_availability": "NONE",
  "refundable_amount": 0,
  "success_redirect": "https://your.success.redirect.com",
  "failure_redirect": "https://your.failure.redirect.com",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.com",
  "failure_callback": "https://your.failure.callback.com",
  "platform": "API",
  "created_from_ip": "103.59.75.157, 172.69.203.75, 18.68.12.102",
  "checkout_url": "https://api.choicepay.ca/payments/6874ce9402f0f25ed8fc66a7/",
  "payoutProcess": false
}
```


# Create Purchase 1

To Initiate a payment, the very first call to make is `/purchases` with the required data in the request body.

To generate a Purchase, you are required to provide the `Brand ID` (in the request body) and `API key` (in the header) Both can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Mandatory parameters in the request body:**

| Fields | **Notes** |
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

## Optional Parameters

### merchantRef

The `merchantRef` parameter, although not mandatory, is strongly advised for merchants to specify. Its inclusion offers two significant advantages for the merchant:

1. **Prevention of Duplicate Requests:** When a `merchantRef` is utilized, it acts as a unique identifier. This means that if a second purchase request is made using the same `merchantRef` (reference number), the system will recognize it and prevent duplicate transactions from occurring. This prevents unintended or duplicate purchases.

2. **Facilitation of Transaction Retrieval:** In situations where the response from the initial purchase request times out or the 'purchaseId' isn't received, having the `merchantRef` allows the merchant to retrieve detailed transaction information. This ensures they can track and access the specific purchase details related to that reference, even if the immediate response was not received.

However, if the merchant does not specify the 'merchantRef' parameter, the platform will automatically assign and use an internal 'purchaseId' as a reference for that transaction.

### Digital Signature (Optional Parameter) :

To ensure authenticity and non-repudiation of the the pay in request, there is an option to digitally sign the pay in request by using the merchant's public key.

**Public key generation :-**

<img src="https://content.pstmn.io/1e198415-45ef-49d9-9dbf-8270bb853dab/aW1hZ2UucG5n" width="1570" height="743">
**Signature generation :-**

This digitial signature is generated by encrypting the following elements of the pay in request:  
Plaintext= Client.email+purchase.currency+ purchase.products.price+brand_id

**Example of encrypt plaintext with public key in java:-**

```java
private String encryptData(String plaintext, PublicKey publicKey) throws Exception {
    Cipher cipher = Cipher.getInstance("RSA");
    cipher.init(Cipher.ENCRYPT_MODE, publicKey);
    byte[] encryptedbytes = cipher.doFinal(message.getBytes());
    return new String(Base64.getEncoder * ().encode(encryptedbytes));
}

```

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
  body: CreatePurchaseRequest2,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreatePurchaseRequest2`](../../doc/models/create-purchase-request-2.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const body: CreatePurchaseRequest2 = {
  client: {
    email: 'test@gmail.com',
    streetAddress: '10 New Burlington Street Apt. 214',
    city: 'Zurich',
    fullName: 'Test test',
    zipCode: 'W1S 3BE',
    country: 'DE',
    dateOfBirth: '1970-07-10',
    stateCode: 'QLD',
    phone: '+447755564318',
  },
  purchase: {
    currency: 'EUR',
    products: [
      {
        name: 'product name',
        price: '16',
      }
    ],
  },
  merchantRef: 'your-order-id',
  paymentMethod: 'BANKTRANSFER',
  brandId: 'your-brandid',
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
};

try {
  const response = await payinApIsApi.createPurchase1(body);

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
"{\r\n    \"purchaseId\": \"66334635a2cf2a7da7b192ab\",\r\n    \"client\": {\r\n        \"bank_account\": \"\",\r\n        \"bank_code\": \"\",\r\n        \"email\": \"test3@gmail.com\",\r\n        \"phone\": \"+447755564318\",\r\n        \"full_name\": \"\",\r\n        \"date_of_birth\": \"1970-07-10\",\r\n        \"personal_code\": \"\",\r\n        \"street_address\": \"asdfsa\",\r\n        \"country\": \"GB\",\r\n        \"city\": \"a\",\r\n        \"zip_code\": \"W1S 3BE\",\r\n        \"shipping_street_address\": \"\",\r\n        \"shipping_country\": \"\",\r\n        \"shipping_city\": \"\",\r\n        \"shipping_zip_code\": \"\",\r\n        \"cc\": [],\r\n        \"bcc\": [],\r\n        \"legal_name\": \"\",\r\n        \"brand_name\": \"\",\r\n        \"registration_number\": \"\",\r\n        \"tax_number\": \"\",\r\n        \"documentId\": \"\",\r\n        \"documentType\": \"\",\r\n        \"bankAccountNumber\": \"\",\r\n        \"bankAccount\": \"\",\r\n        \"bankCode\": \"\",\r\n        \"description\": \"\",\r\n        \"stateCode\": \"QLD\"\r\n    },\r\n    \"updated_on\": 1714636341,\r\n    \"type\": \"purchase\",\r\n    \"paymentMethod\": \"BANKTRANSFER\",\r\n    \"amountUnit\": \"MAJOR\",\r\n    \"errorMsg\": \"\",\r\n    \"redirectType\": \"GET\",\r\n    \"force_recurring\": false,\r\n    \"created_on\": 1714636341,\r\n    \"merchantRef\": \"66334635a2cf2a7da7b192ab\",\r\n    \"merchantName\": \"merchant002\",\r\n    \"feesDeducted\": 0.3,\r\n    \"purchaseIdShortCode\": “4000013\",\r\n    \"purchase\": {\r\n        \"currency\": \"JPY\",\r\n        \"products\": [\r\n            {\r\n                \"name\": \"test\",\r\n                \"quantity\": 1.0,\r\n                \"price\": 5000.0,\r\n                \"discount\": 0,\r\n                \"tax_percent\": \"0.00\"\r\n            }\r\n        ],\r\n        \"total\": 5000.0,\r\n        \"language\": \"en\",\r\n        \"notes\": \"\",\r\n        \"debt\": 0,\r\n        \"total_formatted\": 1.0,\r\n        \"request_client_details\": [],\r\n        \"timezone\": \"MIT\",\r\n        \"email_message\": \"\"\r\n    },\r\n    \"payment\": {\r\n        \"is_outgoing\": false,\r\n        \"payment_type\": \"PURCHASE\",\r\n        \"amount\": 5000.0,\r\n        \"currency\": \"JPY\",\r\n        \"net_amount\": 5000.0,\r\n        \"fee_amount\": 0.0,\r\n        \"pending_amount\": 0.0,\r\n        \"pending_unfreeze_on\": null,\r\n        \"description\": \"\",\r\n        \"paid_on\": 1714636341,\r\n        \"remote_paid_on\": 1714636341\r\n    },\r\n    \"issuer_details\": {\r\n        \"website\": \"\",\r\n        \"legal_street_address\": \"\",\r\n        \"legal_country\": \"\",\r\n        \"legal_city\": \"\",\r\n        \"legal_zip_code\": \"\",\r\n        \"bank_accounts\": [\r\n            {\r\n                \"bank_account\": \"\",\r\n                \"bank_code\": \"\"\r\n            }\r\n        ],\r\n        \"legal_name\": \"gdhnb\",\r\n        \"brand_name\": \"gdhnb\",\r\n        \"registration_number\": \"\",\r\n        \"tax_number\": \"\"\r\n    },\r\n    \"transaction_data\": {\r\n        \"payment_method\": \"\",\r\n        \"flow\": \"payform\",\r\n        \"extra\": {\r\n            \"amount\": 5000.0,\r\n            \"masked_pan\": \"BANKTRANSFER\"\r\n        },\r\n        \"country\": \"\",\r\n        \"attempts\": [\r\n            {\r\n                \"client_ip\": \"103.59.75.41\",\r\n                \"type\": \"execute\",\r\n                \"payment_method\": \"BANKTRANSFER\",\r\n                \"flow\": \"payform\",\r\n                \"successful\": true,\r\n                \"country\": \"BANKTRANSFER\",\r\n                \"processing_time\": 1714636341,\r\n                \"extra\": {\r\n                    \"amount\": 5000.0,\r\n                    \"masked_pan\": \"BANKTRANSFER\"\r\n                }\r\n            }\r\n        ]\r\n    },\r\n    \"status\": \"PAYMENT_IN_PROCESS\",\r\n    \"status_history\": [\r\n        {\r\n            \"status\": \"created\",\r\n            \"timestamp\": 1714636341\r\n        },\r\n        {\r\n            \"status\": \"pending_execute\",\r\n            \"timestamp\": 1714636341\r\n        },\r\n        {\r\n            \"status\": \"payment_in_process\",\r\n            \"timestamp\": 1714636341\r\n        }\r\n    ],\r\n    \"is_test\": false,\r\n    \"brand_id\": \"76fad4ea-2ba2-4511-8989-3bed04e7d5bb\",\r\n    \"send_receipt\": false,\r\n    \"is_recurring_token\": false,\r\n    \"skip_capture\": false,\r\n    \"reference_generated\": \"PS8937\",\r\n    \"issued\": \"2024-05-02\",\r\n    \"due\": 1714636341,\r\n    \"refund_upto\": 0,\r\n    \"cc_descriptor\": \"\",\r\n    \"fraudScore\": \"NA\",\r\n    \"trustScore\": \"NA\",\r\n    \"payInBankDetails\": {\r\n        \"accountName\": \"ｴｱｰｳｵﾚﾂｸｽｼﾞｬﾊﾟﾝｶﾌﾞｼｷｶｲｼｬ\",\r\n        \"accountNumber\": \"3194368\",\r\n        \"bankName\": \"MUFG BANK, LTD. 三菱UFJ銀行\",\r\n        \"swiftCode\": \"BOTKJPJT\",\r\n        \"branchName\": \"ワカタケ\",\r\n        \"accountType\": \"CHECKING\",\r\n        \"payment_routing_parameters\": {\r\n            \"BANK_CODE\": \"0005\",\r\n            \"BRANCH_CODE\": \"809\"\r\n        }\r\n    },\r\n    \"refund_availability\": \"NONE\",\r\n    \"refundable_amount\": 0.0,\r\n    \"success_redirect\": \"https://test.com/getResponse.jsp?success=true\",\r\n    \"failure_redirect\": \"https://test.com/getResponse.jsp?success=false\",\r\n    \"cancel_redirect\": \"\",\r\n    \"success_callback\": \"https://test1.com\",\r\n    \"failure_callback\": \"https://test2.com\",\r\n    \"platform\": \"API\",\r\n    \"created_from_ip\": \"103.59.75.41\",\r\n    \"checkout_url\": \"https://staging.paysecure.net/payments/66334635a2cf2a7da7b192ab/\"\r\n}"
```


# Get Status 6

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
async getStatus6(
  purchaseId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success22>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `purchaseId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success22`](../../doc/models/success-22.md).

## Example Usage

```ts
const purchaseId = 'purchaseId2';

try {
  const response = await payinApIsApi.getStatus6(purchaseId);

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
  "paymentMethod": "BANKTRANSFER",
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
        "quantity": 1.0,
        "price": 10.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 10.0,
    "language": "en",
    "notes": "",
    "debt": 0,
    "total_formatted": 1.0,
    "expireInMin": "35",
    "request_client_details": [],
    "timezone": "MIT",
    "email_message": ""
  },
  "payment": {
    "is_outgoing": false,
    "payment_type": "PURCHASE",
    "amount": 10.0,
    "currency": "INR",
    "net_amount": 10.0,
    "fee_amount": 0.0,
    "pending_amount": 0.0,
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
      "amount": 10.0,
      "masked_pan": "BANKTRANSFER"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "103.59.75.113",
        "type": "execute",
        "payment_method": "BANKTRANSFER",
        "flow": "payform",
        "successful": true,
        "country": "BANKTRANSFER",
        "processing_time": 1724147324,
        "extra": {
          "amount": 10.0,
          "masked_pan": "BANKTRANSFER"
        }
      }
    ]
  },
  "status": "PAID",
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
    },
    {
      "status": "paid",
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
  "refund_availability": "NONE",
  "refundable_amount": 10.0,
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

