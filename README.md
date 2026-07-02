
# Getting Started with Paysecure API Documentation - Live

## Introduction

### Overview

---


Paysecure is a payment gateway optimization and intelligence service that merchants can use to provide a remote and frictionless payment experience.

This documentation will help you get started with integrating Paysecure but if you have any questions, please do not hesitate to reach out to us via email at [info@paysecure.net](https://)

Please be advised that our support team is only available during standard business hours.

### Environments

---


These are the BaseUrls for the APIs on different environments:

| **Environment** | **Base URL** |
| --- | --- |
| Production | [https://api.paysecure.net/api/v1](https://) |
| Sandbox | [https://api.paysecure.net/api/v1](https://)  <br>`Note: set the Sandbox flag true (checked) in your merchant account. As shown in the image below` |

### Authentication

---


To access the API, you must acquire your unique API key from the merchant dashboard -> API Keys section in your account. Make sure to use this key as a **bearer token** in the Authorization header for every request you send.

`AUTHORIZATION: Bearer Token`

`Token: {{APIKey}} .`

Access your sandbox API key credentials by navigating to your merchant login and checking the 'is sandbox' option, located in the top right corner under merchant profile.

<img src="https://content.pstmn.io/dfe64a66-8699-45c8-9f10-b00f7df380b7/U2NyZWVuc2hvdCAyMDIzLTA5LTE1IGF0IDE2LjU2LjQyLnBuZw==">


To get to the live API key, uncheck the **'Is Sandbox'** option in the top right corner of your merchant dashboard. After unchecking, the page will refresh, and you can generate an API key for live transactions in this environment."

<img src="https://content.pstmn.io/afa2574d-8438-4a63-9b29-81feb0f755e5/U2NyZWVuc2hvdCAyMDIzLTA5LTE1IGF0IDE3LjE0LjI4LnBuZw==">


Reiterating, the API keys in Sandbox mode are for testing (when 'is sandbox' is CHECKED in the top right corner under merchant profile). The live API key credentials are for processing actual card transactions in Live mode (when 'is sandbox' is UNCHECKED in the same location)

### Request Headers

---


Use these headers on every API call unless noted.

| Header | Value | Required | Notes |
| --- | --- | --- | --- |
| `Content-Type` | `application/json` | Yes | All endpoints. Send JSON payloads. |
| `Authorization` | `Bearer {MERCHANT_API_KEY}` | Yes | All endpoints.  <br>Replace with your merchant API key. |
| `BrandId` | `{YOUR_BRAND_ID}` | Conditional | **Session** and **Customer**APIs.  <br>optional in customer APIs but Mandatory in Session APIs |

## Install the Package

Run the following command from your project directory to install the package from npm:

```bash
npm install ps-apimatic-sdk@0.0.1
```

For additional package details, see the [Npm page for the ps-apimatic-sdk@0.0.1 npm](https://www.npmjs.com/package/ps-apimatic-sdk/v/0.0.1).

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/README.md#environments) | The API environment. <br> **Default: `Environment.Production`** |
| timeout | `number` | Timeout for API calls.<br>*Default*: `30000` |
| httpClientOptions | [`Partial<HttpClientOptions>`](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/http-client-options.md) | Stable configurable http client options. |
| unstableHttpClientOptions | `any` | Unstable configurable http client options. |
| logging | [`PartialLoggingOptions`](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/partial-logging-options.md) | Logging Configuration to enable logging |
| bearerAuthCredentials | [`BearerAuthCredentials`](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/auth/oauth-2-bearer-token.md) | The credential object for bearerAuth |

The API client can be initialized as follows:

### Code-Based Client Initialization

```ts
import { Client, Environment, LogLevel } from 'ps-apimatic-sdk';

const client = new Client({
  bearerAuthCredentials: {
    accessToken: 'AccessToken'
  },
  timeout: 30000,
  environment: Environment.Production,
  logging: {
    logLevel: LogLevel.Info,
    logRequest: {
      logBody: true
    },
    logResponse: {
      logHeaders: true
    }
  },
});
```

### Configuration-Based Client Initialization

```ts
import * as path from 'path';
import * as fs from 'fs';
import { Client } from 'ps-apimatic-sdk';

// Provide absolute path for the configuration file
const absolutePath = path.resolve('./config.json');

// Read the configuration file content
const fileContent = fs.readFileSync(absolutePath, 'utf-8');

// Initialize client from JSON configuration content
const client = Client.fromJsonConfig(fileContent);
```

See the [Configuration-Based Client Initialization](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/configuration-based-client-initialization.md) section for details.

### Environment-Based Client Initialization

```ts
import * as dotenv from 'dotenv';
import * as path from 'path';
import * as fs from 'fs';
import { Client } from 'ps-apimatic-sdk';

// Optional - Provide absolute path for the .env file
const absolutePath = path.resolve('./.env');

if (fs.existsSync(absolutePath)) {
  // Load environment variables from .env file
  dotenv.config({ path: absolutePath, override: true });
}

// Initialize client using environment variables
const client = Client.fromEnvironment(process.env);
```

See the [Environment-Based Client Initialization](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/environment-based-client-initialization.md) section for details.

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| Production | **Default** |

## Authorization

This API uses the following authentication schemes.

* [`bearer (OAuth 2 Bearer token)`](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/auth/oauth-2-bearer-token.md)

## List of APIs

* [Pay in API](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/controllers/pay-in-api.md)
* [Pay Out API](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/controllers/pay-out-api.md)
* [Get Balance API](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/controllers/get-balance-api.md)
* [Refund API](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/controllers/refund-api.md)
* [🌎 Paypal Wallet](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/controllers/paypal-wallet.md)
* [💳 Virtual Cards Payout](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/controllers/virtual-cards-payout.md)
* [Trust Score](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/controllers/trust-score.md)
* [Cashier AP Is](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/controllers/cashier-ap-is.md)
* [Transaction Reporting](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/controllers/transaction-reporting.md)
* [Get Balance API V2-Orchestration](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/controllers/get-balance-api-v2-orchestration.md)
* [Global Collection](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/controllers/global-collection.md)
* [Payout Manual Review](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/controllers/payout-manual-review.md)
* [AP Is](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/controllers/ap-is.md)
* [Payout](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/controllers/payout.md)
* [Payin](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/controllers/payin.md)
* [API](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/controllers/api.md)

## SDK Infrastructure

### Configuration

* [HttpClientOptions](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/http-client-options.md)
* [RetryConfiguration](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/retry-configuration.md)
* [ProxySettings](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/proxy-settings.md)
* [Configuration-Based Client Initialization](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/configuration-based-client-initialization.md)
* [Environment-Based Client Initialization](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/environment-based-client-initialization.md)
* [PartialLoggingOptions](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/partial-logging-options.md)
* [PartialRequestLoggingOptions](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/partial-request-logging-options.md)
* [PartialResponseLoggingOptions](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/partial-response-logging-options.md)
* [LoggerInterface](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/logger-interface.md)

### HTTP

* [HttpRequest](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/http-request.md)

### Utilities

* [ApiResponse](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/api-response.md)
* [ApiError](https://www.github.com/sdks-io/ps-apimatic-js-sdk/tree/0.0.1/doc/api-error.md)

