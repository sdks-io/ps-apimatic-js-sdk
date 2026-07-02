
# Get Single Merchant

*This model accepts additional fields of type unknown.*

## Structure

`GetSingleMerchant`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `string` | Required | - |
| `data` | [`Data9`](../../doc/models/data-9.md) | Required | - |
| `message` | `string` | Required | - |
| `reqId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { GetSingleMerchant } from 'ps-apimatic-sdk';

const getSingleMerchant: GetSingleMerchant = {
  status: 'success',
  data: {
    merchantId: 4230,
    email: 'test17@paysecure.co',
    name: 'testprithvimerchant17',
    legalName: 'Test Prithvirajtest2 Merchants Pvt Ltd',
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
    contactPhone: '+919876543210',
    contactName: 'Prithvi Kashyap',
    officerTitle: 'Director',
    officerName: 'Prithvi Kashyap',
    defaultCurrency: 'EUR',
    defaultTimezone: 'UTC',
    allowGlobalCollection: true,
    isLiveTransactionAllowed: true,
    allowedPaymentMethods: [
      'PayByBank'
    ],
    allowedCurrencies: [
      'AED',
      'GBP'
    ],
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  message: 'Merchant details fetched successfully',
  reqId: '123456',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

