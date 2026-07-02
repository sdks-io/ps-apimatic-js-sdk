# Refund API

```ts
const refundApi = new RefundApi(client);
```

## Class Name

`RefundApi`


# Refund

This API is used to initate refund of the purchases that have status as `PAID`

Once the refund has been initiated, the status of the purchase would become `REFUND_IN_PROCESS` and once the refund has been approved by the bank, the status woud become `REFUNDED`

Purchase ID is **mandatory** for this API.

If due to some reason, the refund has failed, the status would again become `PAID`

### Response Examples

In the response examples you can see instances of both `successful` and `unsuccessful` in refund of purchases.

:information_source: **Note** This endpoint does not require authentication.

```ts
async refund(
  requestOptions?: RequestOptions
): Promise<ApiResponse<RefundPending1>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`RefundPending1`](../../doc/models/refund-pending-1.md).

## Example Usage

```ts
try {
  const response = await refundApi.refund();

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
  "status": "REFUND_IN_PROCESS",
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
    },
    {
      "status": "refund_in_process",
      "timestamp": 1690302819
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

