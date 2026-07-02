# 💳 Virtual Cards Payout

```ts
const mVirtualCardsPayoutApi = new MVirtualCardsPayoutApi(client);
```

## Class Name

`MVirtualCardsPayoutApi`

## Methods

* [Create Customer](../../doc/controllers/virtual-cards-payout.md#create-customer)
* [Get Customer](../../doc/controllers/virtual-cards-payout.md#get-customer)
* [Create Pay Out](../../doc/controllers/virtual-cards-payout.md#create-pay-out)


# Create Customer

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
async createCustomer(
  brandId: string,
  body: CreateCustomerRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success19>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `brandId` | `string` | Header, Required | - |
| `body` | [`CreateCustomerRequest`](../../doc/models/create-customer-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success19`](../../doc/models/success-19.md).

## Example Usage

```ts
const brandId = 'brand_id_value';

const body: CreateCustomerRequest = {
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
  extraParam: {
    param1: 'value1',
    param2: 'value2',
    param3: 'value3',
    param4: 'value4',
  },
};

try {
  const response = await mVirtualCardsPayoutApi.createCustomer(
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
  const response = await mVirtualCardsPayoutApi.getCustomer(
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


# Create Pay Out

To Initiate a payout, the very first call to make is /payout/

with the required data in the request body.

To generate a Payout, you are required to provide the `API key` (in the header) can be located in the Dashboard section of your merchant account login.

The request body structure is shown on the request body of the example request shown here.

:information_source: **Note** This endpoint does not require authentication.

```ts
async createPayOut(
  body: CreatePayOutRequest5,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Success21>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreatePayOutRequest5`](../../doc/models/create-pay-out-request-5.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Success21`](../../doc/models/success-21.md).

## Example Usage

```ts
const body: CreatePayOutRequest5 = {
  client: {
    customerId: '684fe5700eb6476b179037aa',
    email: 'customer141@email.uk',
    phone: '1234567890',
    fullName: 'Test Person-uk',
    country: 'SG',
  },
  payoutMethod: 'Payout-virtual-cards',
  amount: 10,
  currency: 'USD',
  purpose: 'payout to test',
  successCallback: 'https://success.com',
  failureCallback: 'https://failure.com',
  extraParam: {
    productType: 'WELFARE',
  },
};

try {
  const response = await mVirtualCardsPayoutApi.createPayOut(body);

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
  "payoutId": "685faaf0b93cc30dd78957c6",
  "client": {
    "customerId": "685fa7d7b93cc30dd78956c1",
    "email": "rahul+7@paysecure.net",
    "phone": "+918839471520",
    "full_name": "Rahul Agarwal",
    "street_address": "Vaishali Jaipur",
    "country": "FR",
    "city": "jaipur",
    "zip_code": "202020",
    "stateCode": "RA"
  },
  "updated_on": 1751100145,
  "payoutMethod": "PAYOUT-VIRTUAL-CARDS",
  "amountUnit": "MAJOR",
  "amount": 5.0,
  "errorMsg": "",
  "purpose": "payout to test",
  "created_on": 1751100145,
  "merchantRef": "685faaf0b93cc30dd78957c6",
  "status": "PAID",
  "status_history": [
    {
      "status": "created",
      "timestamp": 1751100145
    },
    {
      "status": "paid",
      "timestamp": 1751100145
    }
  ],
  "currency": "EUR",
  "paymentOn": 1751100145,
  "taxAmount": 0.0,
  "taxPercent": 0.0,
  "redirectType": "POST",
  "extraParam": {
    "productType": "HOTAC"
  },
  "success_callback": "https://success.com",
  "failure_callback": "https://failure.com"
}
```

