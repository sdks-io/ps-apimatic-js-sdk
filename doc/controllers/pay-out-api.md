# Pay Out API

```ts
const payOutApi = new PayOutApi(client);
```

## Class Name

`PayOutApi`

## Methods

* [Create Pay Out](../../doc/controllers/pay-out-api.md#create-pay-out)
* [Get Status](../../doc/controllers/pay-out-api.md#get-status)
* [Create Pay Out 1](../../doc/controllers/pay-out-api.md#create-pay-out-1)
* [Get Status 1](../../doc/controllers/pay-out-api.md#get-status-1)
* [Create Payout 2](../../doc/controllers/pay-out-api.md#create-payout-2)
* [Create Pay Out 3](../../doc/controllers/pay-out-api.md#create-pay-out-3)
* [Get Status 2](../../doc/controllers/pay-out-api.md#get-status-2)
* [Create Pay Out 11](../../doc/controllers/pay-out-api.md#create-pay-out-11)
* [Get Status 3](../../doc/controllers/pay-out-api.md#get-status-3)
* [Payout API](../../doc/controllers/pay-out-api.md#payout-api)
* [Payout](../../doc/controllers/pay-out-api.md#payout)
* [Payout API 1](../../doc/controllers/pay-out-api.md#payout-api-1)
* [New Request](../../doc/controllers/pay-out-api.md#new-request)
* [Create Pay Out 21](../../doc/controllers/pay-out-api.md#create-pay-out-21)
* [Get Status 4](../../doc/controllers/pay-out-api.md#get-status-4)


# Create Pay Out

To Initiate a payment, the very first call to make is /payout/

with the required data in the request body.

To generate a Payout, you are required to provide the `API key` (in the header) can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a Payout request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.email | An Identifier for a user |
| client.full_name | An Identifier for a user |
| client.country | CA |
| payoutMethod | PAYOUT-INTERAC-ETRANSFER |
| Currency | CAD |
| Amount | Payout Amount |
| Purpose | Transfer Reversed |

:information_source: **Note** This endpoint does not require authentication.

```ts
async createPayOut(
  brandId: string,
  body: CreatePayOutRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<CreatePayoutSuccess>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `brandId` | `string` | Header, Required | - |
| `body` | [`CreatePayOutRequest`](../../doc/models/create-pay-out-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`CreatePayoutSuccess`](../../doc/models/create-payout-success.md).

## Example Usage

```ts
const brandId = 'your-brand-id';

const body: CreatePayOutRequest = {
  client: {
    email: 'gouridausa+2@gmail.com',
    streetAddress: 'test test',
    city: '123',
    fullName: 'Pay secure',
    zipCode: '234567',
    country: 'CA',
    stateCode: 'CT',
    phone: '1111111111',
  },
  payoutMethod: 'PAYOUT-INTERAC-ETRANSFER',
  purpose: 'entertainment',
  currency: 'CAD',
  amount: 18,
  successRedirect: 'https://success.com',
  failureRedirect: 'https://failure.com',
  pendingRedirect: 'https://pending.com',
};

try {
  const response = await payOutApi.createPayOut(
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
  "_type": "Payout",
  "payoutId": "69cd1236e36738557e988399",
  "client": {
    "_type": "PClientDetails",
    "customerId": "NA",
    "email": "gouridausa+2@gmail.com",
    "phone": "+14378817874",
    "full_name": "Ashish Mistry",
    "date_of_birth": null,
    "street_address": "test test",
    "country": "CA",
    "city": "Torronto",
    "zip_code": "234567",
    "documentId": null,
    "documentType": null,
    "spei_clabe": null,
    "spei_debitCard": null,
    "spei_mobileNo": null,
    "stateCode": "CT"
  },
  "updated_on": 1775047222,
  "payoutMethod": "PAYOUT-INTERAC-ETRANSFER",
  "beneficiaryDetail": null,
  "amountUnit": "MAJOR",
  "amount": 5,
  "errorMsg": "paid",
  "issued": "2026-04-01",
  "responseMsg": null,
  "purpose": "Transfer Interac",
  "created_on": 1775047222,
  "custUniqueId": "ashishm.21190@gmail.com",
  "amount_in_usd": 3.6,
  "merchantRef": "69cd1236e36738557e988399",
  "instruction": null,
  "merchant_id": null,
  "usePrivateKey": null,
  "merchantName": null,
  "agentId": 0,
  "parentId": 0,
  "whiteId": 0,
  "year": null,
  "month": null,
  "day": null,
  "hour": 12,
  "bankid": null,
  "setCurr": "CAD",
  "pspReference": null,
  "bankmid": null,
  "bankname": null,
  "status": "paid",
  "status_history": [
    {
      "_type": "Status",
      "status": "created",
      "timestamp": 1775047222,
      "updatedBy": null,
      "paidReason": null
    },
    {
      "_type": "Status",
      "status": "paid",
      "timestamp": 1775047239,
      "updatedBy": null,
      "paidReason": null
    }
  ],
  "viewedOn": null,
  "currency": "CAD",
  "actionStatus": {
    "_type": "ApiError",
    "message": null,
    "actualMessage": null,
    "merchantName": null,
    "code": "success",
    "status": "paid",
    "callback_url": null,
    "method": null,
    "beneficiaryId": null,
    "profileId": null,
    "payInBankDetail": null,
    "pix_payload": null,
    "payInDetails": {
      "_type": "PayInDetail",
      "name": "INTERAC E-TRANSFER",
      "emailAddress": "ashishm.21190@gmail.com",
      "secretQA": "q691236367385579883992851",
      "secretAnswer": "a691236367385579883992851",
      "reference_number": null,
      "payment_method": null,
      "transaction_expiry": null,
      "qrCode": null,
      "gpayUri": null,
      "phonepeUri": null,
      "paytmUri": null,
      "intentUri": null,
      "generatedLink": null,
      "instruction": null,
      "paymentUrl": null,
      "script": null,
      "clabe": null,
      "beneficiary": null,
      "amount": null,
      "linkExpiresOn": null,
      "cardExpiresOn": null,
      "subStatus": null
    },
    "balance": null,
    "vab": null,
    "authKey": null,
    "methodExecutionTime": null,
    "password": null,
    "salt": null,
    "nextCall": null,
    "nextURL": null,
    "descriptor": null,
    "currentTime": 1775047239,
    "custVerificationString": null,
    "instructions": null,
    "trustScore": null,
    "trustLevel": null,
    "no_Of_Cust_Hits": null,
    "no_Of_Hits": null,
    "referer": null,
    "clientIp": null,
    "merchantIp": null,
    "isS2s": null,
    "otp": null,
    "userDeviceId": null,
    "isAllowed": null,
    "logo_url": null,
    "transactionExpireInMin": null,
    "mandateReferenceId": null
  },
  "fx_Currency": null,
  "fx_Amount": null,
  "referer": null,
  "clientIp": "95.217.22.130",
  "merchantIp": "95.217.22.130",
  "transFees": null,
  "MDR": null,
  "ruleName": "Rule_Not_Applied",
  "cascade_Num": null,
  "conversionRiskFactorApplied": null,
  "feesDeducted": 0,
  "signature": null,
  "puId": "",
  "uId": 0,
  "authKey": "",
  "currency_conversion": null,
  "success_callback": "",
  "failure_callback": "",
  "success_redirect": "https://success.com",
  "failure_redirect": "https://failure.com",
  "pending_redirect": "https://pending.com"
}
```


# Get Status

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
async getStatus(
  payoutId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<GetSuccessStatus>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payoutId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`GetSuccessStatus`](../../doc/models/get-success-status.md).

## Example Usage

```ts
const payoutId = 'payoutId4';

try {
  const response = await payOutApi.getStatus(payoutId);

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
  "payoutId": "66bf2e76e3defc36cd575481",
  "client": {
    "customerId": "NA",
    "email": "ashishm.21190@gmail.com",
    "phone": "+14377717874",
    "full_name": "Ashish Mistry",
    "country": "CA"
  },
  "updated_on": 1723805728,
  "payoutMethod": "PAYOUT-INTERAC-ETRANSFER",
  "amountUnit": "MAJOR",
  "amount": 12,
  "errorMsg": "",
  "purpose": "test payout",
  "created_on": 1723805302,
  "merchantRef": "66bf2e76e3defc36cd575481",
  "merchantName": "arunsinghal",
  "status": "PAID",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1723805302
    },
    {
      "status": "payout_in_process",
      "timestamp": 1723805310
    },
    {
      "status": "paid",
      "timestamp": 1723805728
    },
    {
      "status": "viewed",
      "timestamp": 1738750221
    }
  ],
  "viewedOn": 1738750221,
  "currency": "USD",
  "paymentOn": 1723805728,
  "payOutDetails": {
    "name": "INTERAC E-TRANSFER",
    "emailAddress": "ashishm.21190@gmail.com",
    "secretQA": "q66276336575481202",
    "secretAnswer": "a66276336575481202"
  },
  "success_callback": "https://webhook.site/d7660184-d724-480c-bad0-cf0480f5518e",
  "failure_callback": "https://webhook.site/d7660184-d724-480c-bad0-cf0480f5518e"
}
```


# Create Pay Out 1

To Initiate a payment, the very first call to make is /payout/

with the required data in the request body.

To generate a Payout, you are required to provide the `API key` (in the header) can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a Payout request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.email or client.phone | An Identifier for a user |
| client.full_name | Full Name of the user |
| client.country | CA |
| payoutMethod | PAYOUT-INTERAC-REQUEST-MONEY |
| Currency | Note this is currency account for which you have balance |
| Amount | amount in CAD |
| Purpose | eg. "Transfer Reversed" |

:information_source: **Note** This endpoint does not require authentication.

```ts
async createPayOut1(
  brandId: string,
  body: CreatePayOutRequest1,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success5>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `brandId` | `string` | Header, Required | - |
| `body` | [`CreatePayOutRequest1`](../../doc/models/create-pay-out-request-1.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success5`](../../doc/models/success-5.md).

## Example Usage

```ts
const brandId = 'your-brand-id';

const body: CreatePayOutRequest1 = {
  client: {
    email: 'ashishm.21190@gmail.com',
    country: 'CA',
    phone: '+14377717874',
    fullName: 'Ashish Mistry',
  },
  purpose: 'Transfer Reversed',
  currency: 'CAD',
  payoutMethod: 'PAYOUT-INTERAC-REQUEST-MONEY',
  amount: 1,
  successCallback: 'https://webhook.site/d7660184-d724-480c-bad0-cf0480f5518e',
  failureCallback: 'https://webhook.site/d7660184-d724-480c-bad0-cf0480f5518e',
};

try {
  const response = await payOutApi.createPayOut1(
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
  "payoutId": "670cb200fcc7f4706acb6759",
  "client": {
    "email": "ashishm.21190@gmail.com",
    "phone": "+14377717874",
    "full_name": "Ashish Mistry",
    "country": "CA"
  },
  "updated_on": 1728885248,
  "payoutMethod": "PAYOUT-INTERAC-REQUEST-MONEY",
  "amountUnit": "MAJOR",
  "amount": 1,
  "errorMsg": "",
  "purpose": "test payout",
  "created_on": 1728885248,
  "merchantRef": "670cb200fcc7f4706acb6759",
  "status": "PAYOUT_IN_PROCESS",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1728885248
    },
    {
      "status": "payout_in_process",
      "timestamp": 1728885253
    }
  ],
  "currency": "CAD",
  "paymentOn": 0,
  "payOutDetails": {
    "emailAddress": "ashishm.21190@gmail.com",
    "secretQA": "q670200747066759362",
    "secretAnswer": "a670200747066759362"
  },
  "success_callback": "https://webhook.site/d7660184-d724-480c-bad0-cf0480f5518e",
  "failure_callback": "https://webhook.site/d7660184-d724-480c-bad0-cf0480f5518e"
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
): Promise<ApiResponse<GetSuccessStatus1>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payoutId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`GetSuccessStatus1`](../../doc/models/get-success-status-1.md).

## Example Usage

```ts
const payoutId = 'payoutId4';

try {
  const response = await payOutApi.getStatus1(payoutId);

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
  "payoutId": "670926784600a76f8d8a1b43",
  "client": {
    "email": "ashishm.21190@gmail.com",
    "phone": "+14377717874",
    "full_name": "Ashish Mistry",
    "country": "CA"
  },
  "updated_on": 1728653103,
  "payoutMethod": "PAYOUT-INTERAC-DEBIT",
  "amountUnit": "MAJOR",
  "amount": 1,
  "errorMsg": "",
  "purpose": "test payout",
  "created_on": 1728652920,
  "merchantRef": "670926784600a76f8d8a1b43",
  "merchantName": "Ajay002",
  "status": "PAID",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1728652920
    },
    {
      "status": "payout_in_process",
      "timestamp": 1728652924
    },
    {
      "status": "paid",
      "timestamp": 1728653103
    },
    {
      "status": "viewed",
      "timestamp": 1729154507
    }
  ],
  "viewedOn": 1729154507,
  "currency": "CAD",
  "paymentOn": 1728653103,
  "payOutDetails": {
    "emailAddress": "ashishm.21190@gmail.com",
    "secretQA": "q6709267846007688143362",
    "secretAnswer": "a6709267846007688143362"
  },
  "success_callback": "https://webhook.site/d7660184-d724-480c-bad0-cf0480f5518e",
  "failure_callback": "https://webhook.site/d7660184-d724-480c-bad0-cf0480f5518e"
}
```


# Create Payout 2

To Initiate a payment, the very first call to make is /payout/

with the required data in the request body.

To generate a Payout, you are required to provide the `API key` (in the header) can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a Payout request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.email client.phone | An Identifier for a user |
| client.full_name | An Identifier for a user |
| client.country | CA |
| payoutMethod | PAYOUT-INTERAC-EXPRESS |
| Currency | CAD |
| Amount | Payout Amount |
| Purpose | Transfer Reversed |

:information_source: **Note** This endpoint does not require authentication.

```ts
async createPayout2(
  brandId: string,
  body: CreatePayOutRequest1,
  requestOptions?: RequestOptions
): Promise<ApiResponse<CreatePayoutSuccess1>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `brandId` | `string` | Header, Required | - |
| `body` | [`CreatePayOutRequest1`](../../doc/models/create-pay-out-request-1.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`CreatePayoutSuccess1`](../../doc/models/create-payout-success-1.md).

## Example Usage

```ts
const brandId = 'your-brand-id';

const body: CreatePayOutRequest1 = {
  client: {
    email: 'ashishm.21190@gmail.com',
    country: 'CA',
    phone: '+14377717874',
    fullName: 'Test Person-uk',
  },
  purpose: 'Transfer Reversed',
  currency: 'CAD',
  payoutMethod: 'PAYOUT-INTERAC-ETRANSFER',
  amount: 10,
  successCallback: 'https://success.com',
  failureCallback: 'https://failure.com',
};

try {
  const response = await payOutApi.createPayout2(
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
  "payoutId": "67efc0586720dd3a164fe8b3",
  "client": {
    "customerId": "NA",
    "email": "ashishm.21190@gmail.com",
    "country": "CA",
    "phone": "+14377717874",
    "full_name": "Test Person-uk"
  },
  "updated_on": 1743765592,
  "payoutMethod": "PAYOUT-INTERAC-EXPRESS",
  "amountUnit": "MAJOR",
  "amount": 10,
  "errorMsg": "",
  "purpose": "test payout",
  "created_on": 1743765592,
  "merchantRef": "67efc0586720dd3a164fe8b3",
  "merchantName": "arunsinghal",
  "status": "PAID",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1743765592
    },
    {
      "status": "paid",
      "timestamp": 1743765610
    },
    {
      "status": "viewed",
      "timestamp": 1744025266
    }
  ],
  "viewedOn": 1744026844,
  "currency": "CAD",
  "paymentOn": 1743765610,
  "success_callback": "https://success.com",
  "failure_callback": "https://failure.com"
}
```


# Create Pay Out 3

To Initiate a payout, the very first call to make is /payout/ API with the required data in the request body.

To generate a PayOut, you are required to provide the `API key` (in the header), which can be located in the Dashboard section of your merchant account login.

The following (see table below) are the mandatory parameters that are required to create a payout request.

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
| payoutMethod | example: PAYOUT-PIX |
| success_redirect | URL to send the user if the transactions is successful. |
| pending_redirect | URL to send the user if the transactions is in pending. |
| failure_redirect | URL to send the user if the transactions is unsuccessful. |
| Purpose | The purpose of doing a payout. |

### Additional **parameters for this usecase:**

| **Parameter** | **Notes** |
| --- | --- |
| client.documentType | Mandatory.  <br>Document Type Supported : cpf, cnpj, evp, email, phone  <br>  <br>cpf is Brazil's tax_id  <br>cnpj is Business tax_id  <br>evp is random key generated by the bank  <br>email is the email which supports pix  <br>phone is the phone number which supports pix |
| client.documentId | Mandatory.  <br>Document value of the type above. |

:information_source: **Note** This endpoint does not require authentication.

```ts
async createPayOut3(
  body: CreatePayOutRequest3,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success8>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreatePayOutRequest3`](../../doc/models/create-pay-out-request-3.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success8`](../../doc/models/success-8.md).

## Example Usage

```ts
const body: CreatePayOutRequest3 = {
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
    documentId: ' 97c1c590-554b-4449-a0f1-8da9f9756937',
    documentType: 'evp',
  },
  purpose: 'payout to test',
  payoutMethod: 'Payout-PIX',
  brandId: '{{merchant_brand_id}}',
  amount: 10,
  currency: 'BRL',
  successRedirect: 'https://test.com/getResponse.jsp?success=true',
  pendingRedirect: 'https://test.com/getResponse.jsp?success=pending',
  failureRedirect: 'https://test.com/getResponse.jsp?success=false',
  successCallback: 'https://test1.com',
  failureCallback: 'https://test2.com',
};

try {
  const response = await payOutApi.createPayOut3(body);

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
  "payoutId": "65f93895c96bae142f7b1765",
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
    "documentId": " 97c1c590-554b-4449-a0f1-8da9f9756937",
    "documentType": "evp"
  },
  "updated_on": 1710831765,
  "payoutMethod": "Payout-PIX",
  "amountUnit": "MAJOR",
  "amount": 10.0,
  "errorMsg": "",
  "created_on": 1710831768,
  "merchantName": "test",
  "status": "PAID",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1710831765
    },
    {
      "status": "paid",
      "timestamp": 1710831768
    }
  ],
  "currency": "BRL",
  "purpose": "payout to test",
  "success_redirect": "https://test.com/getResponse.jsp?success=true",
  "pending_redirect": "https://test.com/getResponse.jsp?success=pending",
  "failure_redirect": "https://test.com/getResponse.jsp?success=false",
  "success_callback": "https://test1.com",
  "failure_callback": "https://test2.com"
}
```


# Get Status 2

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
async getStatus2(
  payoutId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success8>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payoutId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success8`](../../doc/models/success-8.md).

## Example Usage

```ts
const payoutId = 'payoutId4';

try {
  const response = await payOutApi.getStatus2(payoutId);

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
  "payoutId": "65f93895c96bae142f7b1765",
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
    "documentId": " 97c1c590-554b-4449-a0f1-8da9f9756937",
    "documentType": "evp"
  },
  "updated_on": 1710831765,
  "payoutMethod": "Payout-PIX",
  "amountUnit": "MAJOR",
  "amount": 10.0,
  "errorMsg": "",
  "created_on": 1710831768,
  "merchantName": "test",
  "status": "PAID",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1710831765
    },
    {
      "status": "paid",
      "timestamp": 1710831768
    }
  ],
  "currency": "BRL",
  "purpose": "payout to test",
  "success_redirect": "https://test.com/getResponse.jsp?success=true",
  "pending_redirect": "https://test.com/getResponse.jsp?success=pending",
  "failure_redirect": "https://test.com/getResponse.jsp?success=false",
  "success_callback": "https://test1.com",
  "failure_callback": "https://test2.com"
}
```


# Create Pay Out 11

To Initiate a payment, the very first call to make is/payout/

with the required data in the request body.

To generate a Payout, you are required to provide the `API key` (in the header) can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a Payout request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.email or client.phone | An Identifier for a user |
| client.full_name |  |
| client.country |  |
| payoutMethod |  |
| Currency | Note this is currency account for which you have balance |
| Amount |  |
| Purpose |  |

:information_source: **Note** This endpoint does not require authentication.

```ts
async createPayOut11(
  body: CreatePayOutRequest4,
  requestOptions?: RequestOptions
): Promise<ApiResponse<CreatePayoutSuccess2>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreatePayOutRequest4`](../../doc/models/create-pay-out-request-4.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`CreatePayoutSuccess2`](../../doc/models/create-payout-success-2.md).

## Example Usage

```ts
const body: CreatePayOutRequest4 = {
  client: {
    email: 'test@gmail.com',
    country: 'EG',
    phone: '9586445444',
    fullName: 'Test Person-uk',
    documentId: '29206260104051',
  },
  purpose: 'test payout',
  currency: 'EGP',
  payoutMethod: 'Payout-fawrypay',
  amount: 20,
  successCallback: 'https://success.com',
  failureCallback: 'https://failure.com',
};

try {
  const response = await payOutApi.createPayOut11(body);

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
  "payoutId": "6687d86dde5d5c0feecf7621",
  "client": {
    "email": "test@gmail.com",
    "phone": "9586445444",
    "full_name": "Test Person-uk",
    "country": "EG",
    "documentId": "29206260104051"
  },
  "updated_on": 1720178797,
  "payoutMethod": "PAYOUT-FAWRYPAY",
  "amountUnit": "MAJOR",
  "amount": 20.0,
  "errorMsg": "",
  "purpose": "test payout",
  "created_on": 1720178797,
  "merchantRef": "6687d86dde5d5c0feecf7621",
  "status": "PAYOUT_IN_PROCESS",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1720178797
    },
    {
      "status": "payout_in_process",
      "timestamp": 1720178799
    }
  ],
  "currency": "EGP",
  "paymentOn": 0,
  "payOutDetails": {
    "instruction": "Please use transaction reference 20514294 with the BTC 77361 at any Fawry store to get cashout within 72 hrs"
  },
  "success_callback": "https://success.com",
  "failure_callback": "https://failure.com"
}
```


# Get Status 3

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
async getStatus3(
  payoutId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<GetSuccessStatus2>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payoutId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`GetSuccessStatus2`](../../doc/models/get-success-status-2.md).

## Example Usage

```ts
const payoutId = 'payoutId4';

try {
  const response = await payOutApi.getStatus3(payoutId);

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
  "payoutId": "6685467c0e5b201a73f91256",
  "client": {
    "email": "test@gmail.com",
    "phone": "9586445444",
    "full_name": "Test Person-uk",
    "country": "EG",
    "documentId": "29206260104051"
  },
  "updated_on": 1720010823,
  "payoutMethod": "PAYOUT-FAWRYPAY",
  "beneficiaryDetail": {
    "bankAccountNumber": "123456789011",
    "upi": "charles.babbage@okhdfc",
    "transferType": "IMPS",
    "ifscCode": "SBIN0001077",
    "payeeName": "deepak singhal"
  },
  "amountUnit": "MAJOR",
  "amount": 20.0,
  "errorMsg": "",
  "purpose": "test payout",
  "created_on": 1720010364,
  "merchantRef": "6685467c0e5b201a73f91256",
  "merchantName": "test",
  "status": "PAID",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1720010364
    },
    {
      "status": "payout_in_process",
      "timestamp": 1720010367
    },
    {
      "status": "viewed",
      "timestamp": 1720010582
    },
    {
      "status": "paid",
      "timestamp": 1720010823
    }
  ],
  "viewedOn": 1720179568,
  "currency": "EGP",
  "paymentOn": 1720010823,
  "success_callback": "https://success.com",
  "failure_callback": "https://failure.com"
}
```


# Payout API

**Payout API Integration (SPEI)**

---


#### 1\. Request Payload Structure

Submit a JSON payload containing:

- `client` (beneficiary details)

- `purpose` (should be `"payout"`)

- `currency` (always `"MXN"`)

- `payoutMethod` (must be `"PAYOUT-SPEI"`)

- `amount` (numeric, in major units)

- Redirect & callback URLs

```json
jsonCopy{
  "client": {
    "email": "ashishm.21190@gmail.com",
    "country": "MX",
    "phone": "+14377717874",
    "full_name": "MARCO ANTONIO FERNANDEZ RAMIREZ",
    "stateCode": "test",
    "spei_clabe": "012180027944986158"
  },
  "purpose": "payout",
  "currency": "MXN",
  "payoutMethod": "PAYOUT-SPEI",
  "amount": 20,
  "success_redirect": "https://test.com/getResponse.jsp?success=true",
  "failure_redirect": "https://test.com/getResponse.jsp?success=false",
  "success_callback": "https://test1.com",
  "failure_callback": "https://test2.com"
}

```

- **client.email**, **client.phone**, **client.full_name**, **client.country**, **client.stateCode**: Required beneficiary/contact info.

- **client.spei_clabe**: 18-digit CLABE of beneficiary’s bank account (validate format client-side to avoid runtime failures).

- **purpose**: Always set to `"payout"`.

- **currency**: Must be `"MXN"`.

- **payoutMethod**: Must be `"PAYOUT-SPEI"`.

- **amount**: Numeric amount (e.g., `20` for MXN 20.00).

- **success_redirect** / **failure_redirect**: URLs for end-user redirect after they click “Return to Merchant” (GET).

- **success_callback** / **failure_callback**: Webhook endpoints for asynchronous payout status notifications.

---


#### 2\. Sample Response & Key Fields

```json
jsonCopy{
  "payoutId": "683d778dc74d23074a56ea94",
  "client": {
    "customerId": "NA",
    "email": "ashishm.21190@gmail.com",
    "phone": "+14377717874",
    "full_name": "MARCO ANTONIO FERNANDEZ RAMIREZ",
    "country": "MX",
    "spei_clabe": "012180027944986155",
    "stateCode": "test"
  },
  "updated_on": 1748858765,
  "payoutMethod": "PAYOUT-SPEI",
  "amountUnit": "MAJOR",
  "amount": 20.0,
  "errorMsg": "This customer can not be processed !",
  "purpose": "test payout",
  "created_on": 1748858765,
  "merchantRef": "683d778dc74d23074a56ea94",
  "status": "ERROR",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1748858765
    },
    {
      "status": "error",
      "timestamp": 1748858765
    }
  ],
  "currency": "MXN",
  "paymentOn": 0,
  "taxAmount": 0.0,
  "taxPercent": 0.0,
  "success_redirect": "https://test.com/getResponse.jsp?success=true",
  "failure_redirect": "https://test.com/getResponse.jsp?success=false",
  "redirectType": "GET",
  "success_callback": "https://test1.com",
  "failure_callback": "https://test2.com"
}

```

- **payoutId** (`string`): Unique PaySecure identifier for this payout request.

- **client.customerId**: `"NA"` for a new beneficiary or your internal customer ID if returning.

- **client.spei_clabe**: Echoed beneficiary CLABE (note: if the CLABE in response differs by a digit, double-check formatting/validation).

- **updated_on / created_on**: Unix timestamps (seconds since epoch).

- **payoutMethod**: `"PAYOUT-SPEI"`.

- **amountUnit**: `"MAJOR"` indicates amount is in MXN major units (no subunit conversion required).

- **amount**: `20.0` (MXN 20.00).

- **errorMsg**: Describes any immediate rejection reason. If non-empty, `status` will be `"ERROR"`.

- **purpose**: Echo of the `"payout"` field or any custom string you passed.

- **merchantRef**: Mirror of `payoutId` by default; can be overwritten if you pass a custom reference.

- **status**: One of:
  
  - `"created"` → request accepted, preparing SPEI transfer
  
  - `"processing"` → SPEI transfer initiated, awaiting Banco de México settlement
  
  - `"success"` → funds successfully delivered
  
  - `"error"` → immediate failure (e.g., invalid CLABE, validation issue)

- **status_history**: Array showing timestamped states from `"created"` → `"processing"` → (`"success"` or `"error"`).

- **paymentOn**: Unix timestamp when the transfer actually occurred (0 if not delivered).

- **redirectType**: Always `"GET"`, meaning customer is redirected via HTTP GET to your provided URL.

- **success_redirect** / **failure_redirect** / **success_callback** / **failure_callback**: Echo of whatever you passed in request.

**Note:** If you see `"status": "ERROR"` and an `errorMsg`, do not retry automatically—inspect the message, correct client data, then reinitiate a new payout request.

---


#### 3\. Handling Payout Webhooks & Status Flow

1. **Configure Webhooks**
   
   - In your PaySecure Dashboard, register your `success_callback` and `failure_callback` URLs (these will receive POSTs once SPEI settles or fails).

2. **Listen for Events**
   
   - `payout.success`: Banco de México confirmed the credit to beneficiary’s CLABE.
   
   - `payout.error`: CLABE invalid, account closed, or transfer rejected.

3. **Update Your Records**
   
   - On `payout.success`: Mark disbursement as complete; notify your finance/operations teams.
   
   - On `payout.error`: Log failure details, alert operations for manual review, and optionally retry after fixing the root cause.

:information_source: **Note** This endpoint does not require authentication.

```ts
async payoutApi(
  body: PayoutApiRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success12>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PayoutApiRequest`](../../doc/models/payout-api-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success12`](../../doc/models/success-12.md).

## Example Usage

```ts
const body: PayoutApiRequest = {
  client: {
    email: 'ashishm.21190@gmail.com',
    country: 'MX',
    phone: '+14377717874',
    fullName: 'MARCO ANTONIO FERNANDEZ RAMIREZ',
    stateCode: 'test',
    speiClabe: '012180027944986158',
  },
  purpose: 'payout',
  currency: 'MXN',
  payoutMethod: 'PAYOUT-SPEI',
  brandId: '{{merchant_brand_id}}',
  amount: 20,
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
};

try {
  const response = await payOutApi.payoutApi(body);

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
  "payoutId": "683d778dc74d23074a56ea94",
  "client": {
    "customerId": "NA",
    "email": "ashishm.21190@gmail.com",
    "phone": "+14377717874",
    "full_name": "MARCO ANTONIO FERNANDEZ RAMIREZ",
    "country": "MX",
    "spei_clabe": "012180027944986155",
    "stateCode": "test"
  },
  "updated_on": 1748858765,
  "payoutMethod": "PAYOUT-SPEI",
  "amountUnit": "MAJOR",
  "amount": 20,
  "errorMsg": "",
  "purpose": "test payout",
  "created_on": 1748858765,
  "merchantRef": "683d778dc74d23074a56ea94",
  "status": "paid",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1748858765
    },
    {
      "status": "paid",
      "timestamp": 1748858765
    }
  ],
  "currency": "MXN",
  "paymentOn": 0,
  "taxAmount": 0,
  "taxPercent": 0,
  "success_redirect": "https://test.com/getResponse.jsp?success=true",
  "failure_redirect": "https://test.com/getResponse.jsp?success=false",
  "redirectType": "GET",
  "success_callback": "https://test1.com",
  "failure_callback": "https://test2.com"
}
```


# Payout

To Initiate a payout, the very first call to make is /payout/ API with the required data in the request body.

To generate a PayOut, you are required to provide the `API key` (in the header), which can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a purchase request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.full_name | Full name of the receiver. Minimum 2 words with atleast 1 character in each word. |
| client.email | An Identifier for a receiver, should be a valid email. |
| client.country | ISO-3166 Country Code. It must be upper case. |
| client.stateCode | ISO-3166-2 State Code. Must be in upper case. |
| client.street_address | street address of the receiver. |
| client.zip_code | zip code of the receiver. |
| client.phone | Phone number of the receiver. Country code is mandatory.  <br>Example: +234999999999 |
| payoutMethod | Payout-MOBILEMONEY |
| Amount | Amount in currency upto 2 decimal points |
| Currency | Note this is currency account for which you have balance. |
| success_redirect | URL to send the user if the payout is successful |
| pending_redirect | URL to send the user if the payout is in progress |
| failure_redirect | URL to send the user if the payout is unsuccessful. |
| Purpose | Purpose of Payout |

:information_source: **Note** This endpoint does not require authentication.

```ts
async payout(
  body: PayoutRequest2,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PayoutRequest2`](../../doc/models/payout-request-2.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const body: PayoutRequest2 = {
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
  purpose: 'Testing payout',
  currency: 'CDF',
  payoutMethod: 'PAYOUT-MOBILEMONEY',
  amount: 100,
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
};

try {
  const response = await payOutApi.payout(body);

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
"{\n    \"payoutId\": \"69ec70c5b7b9052cc4823367\",\n    \"client\": {\n        \"customerId\": \"NA\",\n        \"full_name\": \"akshaya singhal\",\n        \"email\": \"akshaya@gmail.com\",\n        \"country\": \"CD\",\n        \"city\": \"London\",\n        \"stateCode\": \"RJ\",\n        \"street_address\": \"10 New Burlington StreetApt. 214\",\n        \"zip_code\": \"W1S 3BE\",\n        \"date_of_birth\": \"1994-31-04\",\n        \"phone\": \"+243999999999\"\n    },\n    \"updated_on\": 1777103045,\n    \"payoutMethod\": \"PAYOUT-MOBILEMONEY\",\n    \"amountUnit\": \"MAJOR\",\n    \"amount\": 100.0,\n    \"errorMsg\": \"\",\n    \"is_test\": false,\n    \"purpose\": \"Testing payout\",\n    \"created_on\": 1777103045,\n    \"merchantRef\": \"69ec70c5b7b9052cc4823367\",\n    \"status\": \"PAID\",\n    \"status_history\": [\n        {\n            \"status\": \"created\",\n            \"timestamp\": 1777103045\n        },\n        {\n            \"status\": \"paid\",\n            \"timestamp\": 1777103045\n        }\n    ],\n    \"currency\": \"CDF\",\n    \"extraFee\": \"0\",\n    \"paymentOn\": 0,\n    \"checkout_url\": \"https://api.choicepay.ca/payout/0685d9437d0eb79e48ee8158542d9918/\",\n    \"taxAmount\": 0.0,\n    \"taxPercent\": 0.0,\n    \"success_redirect\": \"https://your.success.redirect.com\",\n    \"pending_redirect\": \"https://your.pending.redirect.com\",\n    \"failure_redirect\": \"https://your.failure.redirect.com\",\n    \"redirectType\": \"POST\",\n    \"sessionId\": \"\",\n    \"surcharge\": 0.0,\n    \"surchargeType\": \"\",\n    \"trxMethod\": \"\",\n    \"success_callback\": \"https://your.success.callback.com\",\n    \"failure_callback\": \"https://your.failure.callback.com\"\n    \"utc_offset\": \"NA\"\n}"
```


# Payout API 1

### Create Payout

This endpoint allows you to initiate a payout transaction.

#### Request Body

- `client` (object, required): Details of the client initiating the payout.
  
  - `email` (string): The email of the client.
  
  - `country` (string): The country of the client.
  
  - `phone` (string): The phone number of the client.
  
  - `full_name` (string): The full name of the client.
  
  - `stateCode` (string): The state code of the client.

- `purpose` (string, required): The purpose of the payout.

- `currency` (string, required): The currency of the payout.

- `payoutMethod` (string, required): The method of payout.

- `amount` (number, required): The amount of the payout.

- `success_callback` (string, required): The URL to which the success callback will be sent.

- `failure_callback` (string, required): The URL to which the failure callback will be sent.

#### Response Body

The response will contain the details of the initiated payout transaction.

:information_source: **Note** This endpoint does not require authentication.

```ts
async payoutApi1(
  body: PayoutApiRequest1,
  requestOptions?: RequestOptions
): Promise<ApiResponse<NewRequest>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PayoutApiRequest1`](../../doc/models/payout-api-request-1.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`NewRequest`](../../doc/models/new-request.md).

## Example Usage

```ts
const body: PayoutApiRequest1 = {
  client: {
    email: 'akshayadeepsinghal@gmail.com',
    country: 'AU',
    phone: '+11111111',
    fullName: 'PAYOUT USER',
    stateCode: 'test',
  },
  purpose: 'test payout',
  currency: 'AUD',
  payoutMethod: 'PAYOUT-NEOSURF',
  amount: 1,
  successCallback: 'https://success.com',
  failureCallback: 'https://failure.com',
};

try {
  const response = await payOutApi.payoutApi1(body);

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
  "payoutId": "683d6fee57aff00ab5faf3c6",
  "client": {
    "customerId": "NA",
    "email": "akshayadeepsinghal@gmail.com",
    "phone": "+11111111",
    "full_name": "PAYOUT USER",
    "country": "AU",
    "stateCode": "test"
  },
  "updated_on": 1748856814,
  "payoutMethod": "PAYOUT-NEOSURF",
  "amountUnit": "MAJOR",
  "amount": 1,
  "errorMsg": "",
  "purpose": "test payout",
  "created_on": 1748856814,
  "merchantRef": "683d6fee57aff00ab5faf3c6",
  "status": "PAID",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1748856814
    },
    {
      "status": "paid",
      "timestamp": 1748856816
    }
  ],
  "currency": "AUD",
  "paymentOn": 1748856816,
  "taxAmount": 0,
  "taxPercent": 0,
  "redirectType": "POST",
  "success_callback": "https://success.com",
  "failure_callback": "https://failure.com"
}
```


# New Request

## Payout Request API

This endpoint allows clients to initiate a payout transaction. It requires specific details about the client and the payout method to process the request successfully.

### Request Format

The request must be sent as a JSON object in the raw body. The following parameters are expected:

- **client**: An object containing client information.
  
  - **email** (string): The email address of the client.
  
  - **country** (string): The country of the client.
  
  - **phone** (string): The phone number of the client.
  
  - **full_name** (string): The full name of the client.

- **purpose** (string): A brief description of the reason for the payout (e.g., "testing payout").

- **currency** (string): The currency in which the payout is to be made (e.g., "AUD").

- **payoutMethod** (string): The method used for the payout (e.g., "PAYOUT-PAYID").

- **amount** (number): The amount to be paid out.

- **extraParam**: An object containing additional payout parameters.
  
  - **payId** (string): The unique identifier for the payout.
  
  - **bankName** (string): The name of the bank associated with the payout.
  
  - **accountName** (string): The name on the account receiving the payout.

- **success_callback** (string): A URL that will be called upon successful completion of the payout.

- **failure_callback** (string): A URL that will be called if the payout fails.

### Response Structure

The response from this endpoint will typically include details about the status of the payout request, which may include:

- A success message or error details.

- A transaction ID for tracking purposes.

- Any additional information relevant to the payout process.

Ensure to handle both success and failure callbacks appropriately based on the response received from this endpoint.

:information_source: **Note** This endpoint does not require authentication.

```ts
async newRequest(
  body: NewRequestRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success18>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`NewRequestRequest`](../../doc/models/new-request-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success18`](../../doc/models/success-18.md).

## Example Usage

```ts
const body: NewRequestRequest = {
  client: {
    email: 'ashishm.21190@gmail.com',
    country: 'CA',
    phone: '7665230591',
    fullName: 'Test Person-uk',
  },
  purpose: 'testing payout',
  currency: 'AUD',
  payoutMethod: 'PAYOUT-PAYID',
  amount: 50,
  extraParam: {
    payId: 'KeU6r2egQmQZeqUfkPYC7HSU1EDrn2GYyU',
    bankName: 'test bank name',
    accountName: 'arun',
  },
  successCallback: '<https://success.com>',
  failureCallback: '<https://failure.com>',
};

try {
  const response = await payOutApi.newRequest(body);

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
  "payoutId": "683d6fee57aff00ab5faf3c6",
  "client": {
    "customerId": "NA",
    "email": "akshayadeepsinghal@gmail.com",
    "phone": "+11111111",
    "full_name": "PAYOUT USER",
    "country": "AU",
    "stateCode": "test"
  },
  "updated_on": 1748856814,
  "payoutMethod": "PAYOUT-PAYID",
  "amountUnit": "MAJOR",
  "amount": 1,
  "errorMsg": "",
  "purpose": "test payout",
  "created_on": 1748856814,
  "merchantRef": "683d6fee57aff00ab5faf3c6",
  "status": "PAID",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1748856814
    },
    {
      "status": "paid",
      "timestamp": 1748856816
    }
  ],
  "currency": "AUD",
  "paymentOn": 1748856816,
  "taxAmount": 0,
  "taxPercent": 0,
  "redirectType": "POST",
  "success_callback": "<https://success.com>",
  "failure_callback": "<https://failure.com>"
}
```


# Create Pay Out 21

To Initiate a payment, the very first call to make is /payout/ with the required data in the request body.

To generate a Payout, you are required to provide the `API key` (in the header) can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

The following (see table below) are the mandatory parameters that are required to create a Payout request.

### **Mandatory parameters in the request body:**

| **Parameter** | **Notes** |
| --- | --- |
| client.full_name | Full name of the receiver. Minimum 2 words with atleast 1 character in each word. |
| client.email | An Identifier for a receiver, should be a valid email. |
| client.country | ISO-3166 Country Code. It must be upper case. |
| client.stateCode | State of the receiver. Must be in upper case. |
| client.street_address | street address of the receiver. |
| client.zip_code | zip code of the receiver. |
| client.phone | Phone number of the receiver. Country code is mandatory.  <br>Example: +234999999999 |
| payoutMethod | Payout-MOBILEMONEY |
| Amount | Amount in currency upto 2 decimal points |
| Currency | Note this is currency account for which you have balance. |
| success_redirect | URL to send the user if the payout is successful |
| pending_redirect | URL to send the user if the payout is in progress |
| failure_redirect | URL to send the user if the payout is unsuccessful. |
| Purpose | Purpose of Payout |

### Required parameters in the request body for this use case:

| **Parameter** | **Notes** |
| --- | --- |
| beneficiaryDetail.bankName | The Bank Name in which the customer want's to credit the money.  <br>  <br>Optional Field.  <br>If passed, only use the mentioned bank names below. Anything else might lead to payout failures.  <br>If you don't want to pass, then you might need to open our checkout_url in the response and user can select the Bank from the dropdown. |
| beneficiaryDetail.bankAccountName | Mandatory Field.  <br>Account Holder's Full Name.  <br>It is advised to have atleast 2 words in the name. |
| beneficiaryDetail.bankAccountCurrency | Optional Field.  <br>The Currency in which the money will be credited. Generally the same as the currency field mentioned above. |
| beneficiaryDetail.bankAccountNumber | Mandatory Field.  <br>Account Holder's Account Number.  <br>This is the account in which the money will be credited. |
| beneficiaryDetail.bankCountryCode | Optional Field.  <br>The country code in which the account exist. Generally the same as the country field mentioned above. |

:information_source: **Note** This endpoint does not require authentication.

```ts
async createPayOut21(
  body: CreatePayOutRequest6,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success23>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreatePayOutRequest6`](../../doc/models/create-pay-out-request-6.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success23`](../../doc/models/success-23.md).

## Example Usage

```ts
const body: CreatePayOutRequest6 = {
  client: {
    email: 'rahul@gmail.com',
    country: 'DE',
    city: 'Zurich',
    stateCode: 'QLD',
    fullName: 'Test test',
    streetAddress: '10 New Burlington Street Apt. 214',
    zipCode: 'W1S 3BE',
    phone: '+448839471521',
    gender: 'M',
    dateOfBirth: '1970-07-10',
  },
  beneficiaryDetail: {
    bankAccountName: 'Rahul Agarwal',
    bankAccountNumber: '645101511808',
    bankCountryCode: 'AT',
  },
  purpose: 'Testing payout',
  currency: 'EUR',
  payoutMethod: 'PAYOUT-BANKTRANSFER',
  amount: 10,
  brandId: 'f2f689d5-ca86-4514-94b9-f41bcdf857d7',
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
};

try {
  const response = await payOutApi.createPayOut21(body);

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
  "payoutId": "65ffadb4c1c83822903a9205",
  "client": {
    "email": "rahul@gmail.com",
    "country": "DE",
    "city": "Zurich",
    "stateCode": "QLD",
    "full_name": "Test test",
    "street_address": "10 New Burlington Street Apt. 214",
    "zip_code": "W1S 3BE",
    "phone": "+448839471521",
    "gender": "M",
    "date_of_birth": "1970-07-10"
  },
  "updated_on": 1711254964,
  "payoutMethod": "Payout-BANKTRANSFER",
  "beneficiaryDetail": {
    "bankAccountName": "Rahul Agarwal",
    "bankAccountNumber": "645101511808",
    "bankName": "ICICI Bank"
  },
  "amountUnit": "MAJOR",
  "amount": 10.0,
  "errorMsg": "Currency Account has insufficient balance.",
  "purpose": "test payout",
  "created_on": 1711254972,
  "merchantRef": "65ffadb4c1c83822903a9205",
  "status": "PAID",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1711254964
    },
    {
      "status": "paid",
      "timestamp": 1711254972
    }
  ],
  "currency": "EUR",
  "success_redirect": "https://your.success.redirect.com",
  "pending_redirect": "https://your.pending.redirect.com",
  "failure_redirect": "https://your.failure.redirect.com",
  "success_callback": "https://your.success.callback.com",
  "failure_callback": "https://your.failure.callback.com"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`FailureError`](../../doc/models/failure-error.md) |


# Get Status 4

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
async getStatus4(
  payoutId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<GetStatus>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payoutId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`GetStatus`](../../doc/models/get-status.md).

## Example Usage

```ts
const payoutId = 'payoutId4';

try {
  const response = await payOutApi.getStatus4(payoutId);

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
  "payoutId": "65ffadb4c1c83822903a9205",
  "client": {
    "email": "customer141@email.uk",
    "full_name": "Test Person-uk",
    "street_address": "Random city address",
    "country": "SG",
    "city": "Singapore",
    "zip_code": "123456",
    "stateCode": "test"
  },
  "updated_on": 1711254964,
  "payoutMethod": "Payout-BANKTRANSFER",
  "beneficiaryDetail": {
    "bankName": "DBS Bank",
    "bankAccountName": "test test",
    "bankAccountCurrency": "SGD",
    "bankAccountNumber": "12345640",
    "bankCountryCode": "SG",
    "swiftCode": "DBSSSGSG",
    "routing_param": {
      "bankCode": "897678",
      "bankBranchCode": "888"
    }
  },
  "amountUnit": "MAJOR",
  "amount": 1000.0,
  "errorMsg": "Currency Account has insufficient balance.",
  "purpose": "test payout",
  "created_on": 1711254972,
  "merchantRef": "65ffadb4c1c83822903a9205",
  "status": "ERROR",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1711254964
    },
    {
      "status": "error",
      "timestamp": 1711254972
    }
  ],
  "currency": "USD",
  "success_callback": "https://success.com",
  "failure_callback": "https://failure.com"
}
```

