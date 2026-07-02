
# Update Merchant Request

*This model accepts additional fields of type unknown.*

## Structure

`UpdateMerchantRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `legalName` | `string` | Required | - |
| `regNo` | `string` | Required | - |
| `websiteUrl` | `string` | Required | - |
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
| `allowedPaymentMethods` | `string[]` | Required | - |
| `allowedCurrencies` | `string[]` | Required | - |
| `isLiveTransactionAllowed` | `boolean` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { UpdateMerchantRequest } from 'ps-apimatic-sdk';

const updateMerchantRequest: UpdateMerchantRequest = {
  legalName: 'Test Prithvirajtest2 Merchants Pvt Ltd',
  regNo: 'CIN123456789',
  websiteUrl: 'https://testprithvi.com',
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
    'AED'
  ],
  isLiveTransactionAllowed: true,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

