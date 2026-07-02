# 🌎 Paypal Wallet

```ts
const mPaypalWalletApi = new MPaypalWalletApi(client);
```

## Class Name

`MPaypalWalletApi`


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
  body: PurchaseRequest1,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PurchaseRequest1`](../../doc/models/purchase-request-1.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const body: PurchaseRequest1 = {
  client: {
    email: 'example@paysecure.net',
    country: 'US',
    city: 'New York',
    stateCode: 'ca',
    streetAddress: 'test test',
    zipCode: '234567',
    phone: '+1 202 555 0185',
  },
  purchase: {
    products: [
      {
        name: 'Apple',
        price: '10',
      }
    ],
  },
  brandId: 'bd69e8a5-adcf-40de-9e43-2b87cb129a5e ',
  merchantRef: 'd9db7ec0-f94c-4a9d-8883-54c19c222d81',
  paymentMethod: 'PAYPAL',
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
};

try {
  const response = await mPaypalWalletApi.purchase(body);

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
"{\n    \"purchaseId\": \"64b032c3c6dccf7d329d9e7e\",\n    \"client\": {\n        \"email\": \"example@paysecure.net\",\n        \"country\": \"US\",\n        \"city\": \"New York\",\n        \"stateCode\": \"ca\",\n        \"street_address\": \"test test\",\n        \"zip_code\": \"234567\",\n        \"phone\": \"+1 202 555 0185\"\n        \"shipping_street_address\": \"\",\n        \"shipping_country\": \"\",\n        \"shipping_city\": \"\",\n        \"shipping_zip_code\": \"\",\n        \"cc\": [],\n        \"bcc\": [],\n        \"legal_name\": \"\",\n        \"brand_name\": \"\",\n        \"registration_number\": \"\",\n        \"stateCode\": \"ca\"\n    },\n    \"updated_on\": 1689268934,\n    \"type\": \"purchase\",\n    \"force_recurring\": false,\n    \"created_on\": 1689268934,\n    \"purchase\": {\n        \"currency\": \"USD\",\n        \"products\": [\n            {\n                \"name\": \"Apple\",\n                \"quantity\": 1,\n                \"price\": 10,\n                \"discount\": 0,\n                \"tax_percent\": \"0.00\"\n            }\n        ],\n        \"total\": 10,\n        \"language\": \"en\",\n        \"notes\": \"\",\n        \"debt\": 0,\n        \"total_formatted\": 1,\n        \"request_client_details\": [],\n        \"timezone\": \"America/Edmonton\",\n        \"email_message\": \"\"\n    },\n    \"issuer_details\": {\n        \"website\": \"\",\n        \"legal_street_address\": \"\",\n        \"legal_country\": \"\",\n        \"legal_city\": \"\",\n        \"legal_zip_code\": \"\",\n        \"bank_accounts\": [\n            {\n                \"bank_account\": \"\",\n                \"bank_code\": \"\"\n            }\n        ],\n        \"legal_name\": \"shoes\",\n        \"brand_name\": \"shoes\",\n        \"registration_number\": \"\",\n        \"tax_number\": \"\"\n    },\n    \"transaction_data\": {\n        \"payment_method\": \"\",\n        \"flow\": \"payform\",\n        \"extra\": {},\n        \"country\": \"\",\n        \"attempts\": []\n    },\n    \"status\": \"CREATED\",\n    \"status_history\": [\n        {\n            \"status\": \"created\",\n            \"timestamp\": 1689268934\n        }\n    ],\n    \"is_test\": false,\n    \"brand_id\": \"bd69e8a5-adcf-40de-9e43-2b87cb129a5e\",\n    \"is_recurring_token\": false,\n    \"reference_generated\": \"PS161\",\n    \"merchantRef\":\"d9db7ec0-f94c-4a9d-8883-54c19c222d81\",\n    \"issued\": \"2023-07-13\",\n    \"due\": 1689268934,\n    \"refund_upto\": 0,\n    \"cc_descriptor\": \"\",\n    \"refund_availability\": \"NONE\",\n    \"refundable_amount\": 0,\n    \"success_redirect\": \"https://your.success.redirect.com\",\n    \"pending_redirect\": \"https://your.pending.redirect.com\",\n    \"failure_redirect\": \"https://your.failure.redirect.com\",\n    \"success_callback\": \"https://your.success.callback.com\",\n    \"failure_callback\": \"https://your.failure.callback.com\"\n    \"platform\": \"API\",\n    \"created_from_ip\": \"149.86.53.48\",\n    \"checkout_url\": \"http://api.paysecure.net/payments/64b032c3c6dccf7d329d9e7e/\",\n    \"direct_post_url\": \"http://api.paysecure.net/api/v1/p/64b032c3c6dccf7d329d9e7e/\"\n}"
```

