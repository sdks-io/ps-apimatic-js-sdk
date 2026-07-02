
# Merchant

*This model accepts additional fields of type unknown.*

## Structure

`Merchant`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `number` | Required | - |
| `email` | `string` | Required | - |
| `name` | `string` | Required | - |
| `legalName` | `string` | Required | - |
| `regNo` | `string` | Required | - |
| `websiteUrl` | `string` | Required | - |
| `category` | `string` | Required | - |
| `iecNo` | `string` | Required | - |
| `tradingStartDate` | `string` | Required | - |
| `dateOfIncorporation` | `string` | Required | - |
| `tradingAddress` | `string` | Required | - |
| `tradingCountry` | `string` | Required | - |
| `tradingState` | `string` | Required | - |
| `tradingPostal` | `string` | Required | - |
| `corporateAddress` | `string` | Required | - |
| `corporateCountry` | `string` | Required | - |
| `corporateState` | `string` | Required | - |
| `corporatePostal` | `string` | Required | - |
| `businessPhone` | `string` | Required | - |
| `contactPhone` | `string` | Required | - |
| `contactName` | `string` | Required | - |
| `officerTitle` | `string` | Required | - |
| `officerName` | `string` | Required | - |
| `defaultCurrency` | `string` | Required | - |
| `defaultTimezone` | `string` | Required | - |
| `allowGlobalCollection` | `boolean` | Required | - |
| `isLiveTransactionAllowed` | `boolean` | Required | - |
| `allowedPaymentMethods` | `string[]` | Required | - |
| `allowedCurrencies` | `string[]` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Merchant } from 'ps-apimatic-sdk';

const merchant: Merchant = {
  merchantId: 4143,
  email: 'test3@paysecure.co',
  name: 'Test Prithvi Merchants',
  legalName: 'Test Prithvi Merchants Pvt Ltd',
  regNo: 'CIN123456789',
  websiteUrl: 'https://testprithvi.com',
  category: '3451',
  iecNo: 'fdsfkshf',
  tradingStartDate: '2022-01-01',
  dateOfIncorporation: '2021-06-15',
  tradingAddress: '123 Trading Street, Mumbai',
  tradingCountry: 'IN',
  tradingState: 'Maharashtra',
  tradingPostal: '400001',
  corporateAddress: '456 Corporate Avenue, Mumbai',
  corporateCountry: 'IN',
  corporateState: 'Maharashtra',
  corporatePostal: '400002',
  businessPhone: '+912212345678',
  contactPhone: '+912212345678',
  contactName: 'Prithvi Kashyap',
  officerTitle: 'Director',
  officerName: 'Prithvi Kashyap',
  defaultCurrency: 'EUR',
  defaultTimezone: 'Asia/Kolkata',
  allowGlobalCollection: false,
  isLiveTransactionAllowed: false,
  allowedPaymentMethods: [
    'MASTER',
    'VISA',
    'JCB'
  ],
  allowedCurrencies: [],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

