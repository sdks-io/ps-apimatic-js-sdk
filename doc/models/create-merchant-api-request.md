
# Create Merchant Api Request

*This model accepts additional fields of type unknown.*

## Structure

`CreateMerchantApiRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `username` | `string` | Required | - |
| `mcc` | `number` | Required | - |
| `iecNo` | `string` | Required | - |
| `allowGlobalCollection` | `boolean` | Required | - |
| `legalName` | `string` | Required | - |
| `name` | `string` | Required | - |
| `regNo` | `string` | Required | - |
| `emailId` | `string` | Required | - |
| `websiteUrl` | `string` | Required | - |
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
| `allowedPaymentMethods` | `string[]` | Required | - |
| `allowedCurrencies` | `string[]` | Required | - |
| `isLiveTransactionAllowed` | `boolean` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreateMerchantApiRequest } from 'ps-apimatic-sdk';

const createMerchantApiRequest: CreateMerchantApiRequest = {
  username: 'testprithvimerchant17',
  mcc: 3451,
  iecNo: 'fdsfkshf',
  allowGlobalCollection: true,
  legalName: 'Test Prithvi Merchants Pvt Ltd',
  name: 'Test Prithvi Merchants 2',
  regNo: 'CIN123456789',
  emailId: 'test17@paysecure.co',
  websiteUrl: 'https://testprithvi.com',
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
  contactPhone: '+919876543210',
  contactName: 'Prithvi Kashyap',
  officerTitle: 'Director',
  officerName: 'Prithvi Kashyap',
  defaultCurrency: 'EUR',
  defaultTimezone: 'UTC',
  allowedPaymentMethods: [
    'PayByBank'
  ],
  allowedCurrencies: [
    'GBP',
    'USD'
  ],
  isLiveTransactionAllowed: true,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

