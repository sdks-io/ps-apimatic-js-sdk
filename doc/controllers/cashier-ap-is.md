# Cashier AP Is

```ts
const cashierApIsApi = new CashierApIsApi(client);
```

## Class Name

`CashierApIsApi`

## Methods

* [Customer](../../doc/controllers/cashier-ap-is.md#customer)
* [Customer 1](../../doc/controllers/cashier-ap-is.md#customer-1)
* [Customer 2](../../doc/controllers/cashier-ap-is.md#customer-2)
* [Purchase Session](../../doc/controllers/cashier-ap-is.md#purchase-session)
* [Payout Session](../../doc/controllers/cashier-ap-is.md#payout-session)
* [Check Status - Payin](../../doc/controllers/cashier-ap-is.md#check-status---payin)
* [Check Status - Payout](../../doc/controllers/cashier-ap-is.md#check-status---payout)


# Customer

**OVERIEW**

The **createCustomer API** allows merchants to create a customer profile on PaySecure when a user visits their website, facilitating a seamless payment experience by pre-filling the customer's details, on the PaySecure Cashier. The API takes in customer information and returns a unique customerID that can be passed in purchase payload, eliminating the need for customers to manually enter their details during transactions.

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
async customer(
  brandId: string,
  body: CustomerRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success19>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `brandId` | `string` | Header, Required | - |
| `body` | [`CustomerRequest`](../../doc/models/customer-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success19`](../../doc/models/success-19.md).

## Example Usage

```ts
const brandId = 'brand_id_value';

const body: CustomerRequest = {
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
  const response = await cashierApIsApi.customer(
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
    if (error instanceof FailureError) {
      console.log(error.result);
    } else if (error instanceof ExistingCustomerError) {
      console.log(error.result);
    }
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

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`FailureError`](../../doc/models/failure-error.md) |
| 401 | Unauthorized | [`ExistingCustomerError`](../../doc/models/existing-customer-error.md) |


# Customer 1

This endpoint makes an HTTP GET request to retrieve customer information from the Paysecure API.

### Request

The request does not include any query parameters, but it uses a raw request body with the following parameter "merchantCustomerId", which will be the customer id on the merchant's side.

### Response

The response of this request can be documented as a JSON schema.

:information_source: **Note** This endpoint does not require authentication.

```ts
async customer1(
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
  const response = await cashierApIsApi.customer1(
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
    if (error instanceof InvalidCustomerError) {
      console.log(error.result);
    }
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

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`InvalidCustomerError`](../../doc/models/invalid-customer-error.md) |


# Customer 2

Whenever a customer or the merchant updates customer details on the merchant site, a PATCH request must be made to synchronize these changes with Paysecure.

This API endpoint allows you to update the customer details using an HTTP PATCH request. The request should be sent to [https://api.paysecure.net/api/v1/{customerId}/patchCustomer](https://api.paysecure.net/api/v1/%7BcustomerId%7D/patchCustomer).

### Request Body

The request body should be in raw format and include the following parameters:

- `fullName` (string): The full name of the customer.

- `emailId` (string): The email address of the customer.

- `dateOfBirth` (string): The date of birth of the customer.

- `phoneNo` (string): The phone number of the customer.

- `city` (string): The city of the customer.

- `stateCode` (string): The state code of the customer.

- `zipCode` (string): The zip code of the customer.

- `address` (string): The address of the customer.

- `country` (string): The country of the customer.

- `createdOn` (string): Time when the customer was created.

- `custRegDate` (string): Customer registration date (Non-Mandatory).

- `successTxn` (string): Success transaction details (Non-Mandatory).

- `lastActivity` (string): Time of the last activity.

- `lastUpdated` (string): Time when the last patch was called.

- `extraParam` (object): Additional parameters including `param1`, `param2`, `param3`, `param4` with their respective values.

### Response

The response will contain the updated customer details or a success message upon successful update.

:information_source: **Note** This endpoint does not require authentication.

```ts
async customer2(
  brandId: string,
  accept: string,
  body: CustomerRequest1,
  paysecureCustomerId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success19>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `brandId` | `string` | Header, Required | - |
| `accept` | `string` | Header, Required | - |
| `body` | [`CustomerRequest1`](../../doc/models/customer-request-1.md) | Body, Required | - |
| `paysecureCustomerId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success19`](../../doc/models/success-19.md).

## Example Usage

```ts
const brandId = 'brand_id_value';

const accept = '*/*';

const body: CustomerRequest1 = {
  fullName: 'Gouri Shankar3',
  emailId: 'gouri@paysecure.com',
  dateOfBirth: '1990-11-27',
  phoneNo: '+91 9413666514',
  city: 'Dausa',
  stateCode: 'Raj',
  zipCode: '202021',
  address: 'Somnath Nagar',
  country: 'IN',
  custRegDate: '2023-12-28',
  successTxn: '33',
};

const paysecureCustomerId = 'PaysecureCustomerId4';

try {
  const response = await cashierApIsApi.customer2(
    brandId,
    accept,
    body,
    paysecureCustomerId
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
  "fullName": "Gouri Shankar3",
  "emailId": "gouri@paysecure.com",
  "dateOfBirth": "1990-11-27",
  "phoneNo": "+91 9413666514",
  "brandID": "brandID",
  "city": "Dausa",
  "zipCode": "202021",
  "address": "Somnath Nagar",
  "country": "IN",
  "stateCode": "Raj",
  "custRegDate": "2023-12-28",
  "successTrans": 0,
  "createdOn": 1763376070,
  "lastUpdated": 1763377024,
  "lastActivity": 1763377024,
  "extraParam": {
    "param1": "value1",
    "param2": "value2",
    "param3": "value3",
    "param4": "value4"
  }
}
```


# Purchase Session

**OVERIEW**

The `createSession` API is designed to initiate a payment session for a customer after their profile has been created via the **createCustomer** API. The session is automatically generated at the backend on the merchant’s checkout URL. This session allows the customer to continue with their transaction without having to manually interact with the session URL, and ensures the session remains active until the payment is completed or the session expires.

This API improves the user experience by reducing transaction failures and enhancing the overall payment process, thus reducing transaction churn rates.

### Mandatory Parameters

| Parameter | Type | Description | Example |
| --- | --- | --- | --- |
| customerId | String | The unique ID of the customer (generated from createCustomer). | 6731a609b6bb5a43ad66c4a6 |

#### Show Crypto Conversion

Additionally, there are some default extra parameters that you can pass for allowing Crypto Conversion on Paysecure's cashier itself.

|  | **Type** | **Description** | **Example** |
| --- | --- | --- | --- |
| extraParam.showCryptoConversion | String | This optional parameter allows customer to see crypto value equivelant to the Fiat amount the customer is planning to pay. | Yes |
| extraParam.cryptoCurrencies | String | Pass here the allowed crypto tokens on the cashier, where customer can see the the conversion value | \[\\"BTC\\",\\"ETH\\",\\"USDT\\",\\"XRP\\",\\"LTC\\",\\"DOGE\\",\\"ETC\\",\\"BNB\\",\\"USDC\\",\\"SOL\\",\\"ADA\\",\\"BCH\\",\\"DASH\\",\\"BTG\\",\\"ZEC\\",\\"DGB\\",\\"EOS\\",\\"XLM\\",\\"TRX\\",\\"QTUM\\",\\"POL\\",\\"SHIB\\",\\"LINK\\",\\"DAI\\",\\"TON\\",\\"AVAX\\",\\"FDUSD\\",\\"ARB\\",\\"OP\\"\] |

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
async purchaseSession(
  brandId: string,
  accept: string,
  body: PurchaseSessionRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success14>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `brandId` | `string` | Header, Required | - |
| `accept` | `string` | Header, Required | - |
| `body` | [`PurchaseSessionRequest`](../../doc/models/purchase-session-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success14`](../../doc/models/success-14.md).

## Example Usage

```ts
const brandId = 'brand_id_value';

const accept = '*/*';

const body: PurchaseSessionRequest = {
  customerId: '68fed1855ebbe829416b08c6',
  merchantRef: 'rahultestcustomer1@paysecure.net',
  currency: 'EUR',
  products: [
    {
      name: 'Product1',
      price: '10',
    },
    {
      name: 'Product2',
      price: '12',
    }
  ],
  totalAmount: '22',
  paymentMethod: 'VISA',
  successRedirect: 'https://merchant-success-page.com/',
  failureRedirect: 'https://merchant-failure-page.com/',
  pendingRedirect: 'https://merchant-pending-page.com/',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  extraParam: {
    param1: 'value1',
    showCryptoConversion: 'yes',
    cryptoCurrencies: '["BTC","ETH","USDT","XRP","LTC","DOGE","ETC","BNB","USDC","SOL","ADA","BCH","DASH","BTG","ZEC","DGB","EOS","XLM","TRX","QTUM","POL","SHIB","LINK","DAI","TON","AVAX","FDUSD","ARB","OP"]',
    param3: 'value3',
    param4: 'value4',
  },
};

try {
  const response = await cashierApIsApi.purchaseSession(
    brandId,
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
    if (error instanceof InvalidSessionError) {
      console.log(error.result);
    }
  }
}
```

## Example Response *(as JSON)*

```json
{
  "sessionUrl": "https://api.paysecure.net/payment-session/691b02b48c73dd76eedaa379/",
  "brandId": "brand_id_value",
  "customerId": "68fed1855ebbe829416b08c6",
  "sessionId": "691b02b48c73dd76eedaa379",
  "expiryOn": 1763378744,
  "createdOn": 1763377844
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`InvalidSessionError`](../../doc/models/invalid-session-error.md) |


# Payout Session

This API is used to initiate a payout session for a customer. By passing the `customerId` (generated via the `createCustomer` API) and specifying `"type": "payout"`, a payout session is started.  
A `sessionURL` is returned in the response, which can be used to redirect the customer to the payout cashier. The customer can then select the payout method, pass required parameters, and the payout will be processed.

#### Parameters:

| **Parameter** | **Type** | **Description** |
| --- | --- | --- |
| **customerId** | string | The unique ID of the customer for whom the payout session is created. This ID is generated by the `createCustomer` API. |
| **currency** | string | The currency of the payout session (e.g., USD). |
| **products** | array | A list of products associated with the payout (e.g., name and price). |
| **totalAmount** | string | The total payout amount (optional. calculated dynamically if value is not passed). |
| **tax_amount** | string | The tax amount to be applied (optional). |
| **tax_percent** | string | The tax percentage to be applied (optional). |
| **type** | string | Should be set to "payout" to initiate a payout session. |
| **success_redirect** | string | The URL where the customer will be redirected after a successful payout. |
| **pending_redirect** | string | The URL where the customer will be redirected after a pending payout. |
| **failure_redirect** | string | The URL where the customer will be redirected after a failed payout attempt. |
| **success_callback** | string | The callback URL for successful payout. |
| **failure_callback** | string | The callback URL for failed payout. |
| **extraParam** | object | Contains additional parameters for the payout session. |
| **extraParam.showCryptoConversion** | string | Set to "yes" to display cryptocurrency conversion. |
| **extraParam.cryptoCurrencies** | string | A list of accepted cryptocurrencies (e.g., BTC, ETH, USDT). |

#### Request Headers:

- **BrandId**: Your unique brand ID (required).

- **Content-Type**: application/json (required).

#### Response:

The API will return a JSON object containing the `sessionURL` that can be used to redirect the customer to the payout cashier.

```json
{
    "sessionUrl": "https://api.paysecure.net/payoutSession/68341ad35f895955355d5452/",
    "brandId": "brand_id_value",
    "customerId": "67c9983fba18400ab6cceb8f",
    "sessionId": "68341ad35f895955355d5452",
    "expiryOn": 1748246103,
    "createdOn": 1748245203
}

```

:information_source: **Note** This endpoint does not require authentication.

```ts
async payoutSession(
  brandId: string,
  accept: string,
  body: PayoutSessionRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PayoutSession>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `brandId` | `string` | Header, Required | - |
| `accept` | `string` | Header, Required | - |
| `body` | [`PayoutSessionRequest`](../../doc/models/payout-session-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PayoutSession`](../../doc/models/payout-session.md).

## Example Usage

```ts
const brandId = 'brand_id_value';

const accept = '*/*';

const body: PayoutSessionRequest = {
  customerId: '67c9983fba18400ab6cceb8f',
  currency: 'USD',
  products: [
    {
      name: 'Product1',
      price: '2',
    }
  ],
  totalAmount: '2',
  taxAmount: '',
  taxPercent: '',
  type: 'payout',
  successRedirect: 'https://your.success.redirect.com',
  pendingRedirect: 'https://your.pending.redirect.com',
  failureRedirect: 'https://your.failure.redirect.com',
  successCallback: 'https://your.success.callback.com',
  failureCallback: 'https://your.failure.callback.com',
  extraParam: {
    showCryptoConversion: 'yes',
    cryptoCurrencies: '["BTC","ETH","USDT","XRP","LTC","DOGE","ETC","BNB","USDC","SOL","ADA","BCH","DASH","BTG","ZEC","DGB","EOS","XLM","TRX","QTUM","POL","SHIB","LINK","DAI","TON","AVAX","FDUSD","ARB","OP"]',
  },
};

try {
  const response = await cashierApIsApi.payoutSession(
    brandId,
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
  "sessionUrl": "https://staging.paysecure.net/payoutSession/68341e385f895955355d5671/",
  "brandId": "{yourBrandID}",
  "customerId": "67c9983fba18400ab6cceb8f",
  "sessionId": "68341e385f895955355d5671",
  "expiryOn": 1748246972,
  "createdOn": 1748246072
}
```


# Check Status - Payin

This endpoint retrieves the details of a session identified by the provided session ID.

> Note that this API only respond once the SessionURL, received in the response for session API, is clicked.

> Once the SessionURL is clicked and the user has selected a payment method and click on "Pay" button, a purchase is created on our backend. If you call this API before that, you will get an error.

:information_source: **Note** This endpoint does not require authentication.

```ts
async checkStatusPayin(
  requestOptions?: RequestOptions
): Promise<ApiResponse<M202Success>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`M202Success`](../../doc/models/m202-success.md).

## Example Usage

```ts
try {
  const response = await cashierApIsApi.checkStatusPayin();

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
    if (error instanceof M400BadRequestError) {
      console.log(error.result);
    } else if (error instanceof M401UnauthorizedError) {
      console.log(error.result);
    }
  }
}
```

## Example Response *(as JSON)*

```json
{
  "purchaseId": "6950e4e3e4a1b008c2fae5c3",
  "client": {
    "customerId": "69034a5a61b460084d20c23b",
    "email": "rahul+23@paysecure.net",
    "phone": "+919634088561",
    "full_name": "Rahul Agarwal",
    "street_address": "Vaishali Jaipur",
    "country": "NA",
    "city": "jaipur",
    "zip_code": "202020",
    "cc": [],
    "bcc": [],
    "stateCode": "RA"
  },
  "updated_on": 1766909180,
  "type": "purchase",
  "paymentMethod": "MASTER,VISA,JCB,AMEX,CRYPTO-BRIDGE,FawryPay,INTERAC-E-TRANSFER,INTERAC-REQUEST-MONEY,MOBILEMONEY,NEOSURF,PAYID,PIX,SPEI,THIRDPARTY-UPI,DISCOVER,BANKTRANSFER,VIRTUAL-IBAN,UPI-COLLECT,UPI-QR,VIRTUAL-ACCOUNT,DINERS,NETBANKING,THIRDPARTY-NETBANKING,MAYA,GCASH,INTERAC-EXPRESS,QRPH",
  "amountUnit": "MAJOR",
  "errorMsg": "This customer can not be processed !",
  "errorCode": "NA",
  "savedCardUsed": "NO",
  "redirectType": "POST",
  "force_recurring": false,
  "created_on": 1766909155,
  "merchantRef": "6950e4e3e4a1b008c2fae5c3",
  "merchantName": "rahul_test",
  "merchantType": "MERCHANT",
  "purchase": {
    "currency": "EUR",
    "products": [
      {
        "name": "NA",
        "quantity": 1.0,
        "price": 22.0,
        "discount": 0,
        "tax_percent": "0.00"
      }
    ],
    "total": 22.0,
    "requestAmount": 22.0,
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
    "extra": {
      "expiry_month": "07",
      "amount": 22.0,
      "card_issuer": "CIAGROUP",
      "masked_pan": "55555555****4444",
      "card_brand": "MASTER",
      "card_issuer_country": "BR",
      "card_type": "DEBIT",
      "cardholder_name": "rahul",
      "expiry_year": "30"
    },
    "country": "",
    "attempts": [
      {
        "client_ip": "183.83.53.214",
        "type": "execute",
        "payment_method": "MASTER",
        "flow": "payform",
        "successful": false,
        "country": "BR",
        "processing_time": 1766909179,
        "extra": {
          "expiry_month": "07",
          "amount": 22.0,
          "card_issuer": "CIAGROUP",
          "masked_pan": "55555555****4444",
          "card_brand": "MASTER",
          "card_issuer_country": "BR",
          "card_type": "DEBIT",
          "cardholder_name": "rahul",
          "expiry_year": "30"
        },
        "error": {
          "message": "This customer can not be processed !",
          "code": "no_mid_found"
        }
      }
    ]
  },
  "status": "ERROR",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1766909155
    },
    {
      "status": "pending_execute",
      "timestamp": 1766909179
    },
    {
      "status": "error",
      "timestamp": 1766909180
    },
    {
      "status": "viewed",
      "timestamp": 1766909186
    }
  ],
  "viewedOn": 1766909186,
  "is_test": false,
  "brand_id": "59c5ed48-caf9-464a-ba54-26e1e02bc1bc",
  "send_receipt": false,
  "is_recurring_token": false,
  "skip_capture": false,
  "reference_generated": "PS334",
  "issued": "2025-12-28",
  "due": 1766909155,
  "refund_upto": 0,
  "cc_descriptor": "",
  "fraudScore": "0",
  "trustScore": "0",
  "extraFee": "0",
  "paidOn": 0,
  "receivedAmt": 0.0,
  "taxAmount": 0.0,
  "surcharge": 0.0,
  "surchargeType": "",
  "sessionId": "6950e4ba5205280b71ac2010",
  "refund_availability": "NONE",
  "refundable_amount": 0.0,
  "success_redirect": "https://google.com/",
  "failure_redirect": "https://google.com/",
  "pending_redirect": "https://google.com/",
  "cancel_redirect": "",
  "success_callback": "https://your.success.callback.com",
  "failure_callback": "https://your.failure.callback.com",
  "platform": "API",
  "checkout_url": "https://api.choicepay.ca/payments/adb6e07f74ec6197ef764909736d478e/",
  "direct_post_url": "https://api.choicepay.ca/api/v1/p/6950e4e3e4a1b008c2fae5c3/",
  "payoutProcess": false
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`M400BadRequestError`](../../doc/models/m400-bad-request-error.md) |
| 401 | Unauthorized | [`M401UnauthorizedError`](../../doc/models/m401-unauthorized-error.md) |


# Check Status - Payout

This API tells you about all the details of a Payout, including its history

### Mandatory

you need to pass the payoutId or session id in the API URL

### Possible Value of Status

| **Status** | **Notes** |
| --- | --- |
| paid | Transaction Successful |
| payout_in_process | payout is under Processing. |
| error | Transaction has Failed. |

:information_source: **Note** This endpoint does not require authentication.

```ts
async checkStatusPayout(
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success29>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success29`](../../doc/models/success-29.md).

## Example Usage

```ts
try {
  const response = await cashierApIsApi.checkStatusPayout();

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

