
# Create Payout Success

*This model accepts additional fields of type unknown.*

## Structure

`CreatePayoutSuccess`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `type` | `string` | Required | - |
| `payoutId` | `string` | Required | - |
| `client` | [`Client12`](../../doc/models/client-12.md) | Required | - |
| `updatedOn` | `number` | Required | - |
| `payoutMethod` | `string` | Required | - |
| `beneficiaryDetail` | `string \| null` | Required | - |
| `amountUnit` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `errorMsg` | `string` | Required | - |
| `issued` | `string` | Required | - |
| `responseMsg` | `string \| null` | Required | - |
| `purpose` | `string` | Required | - |
| `createdOn` | `number` | Required | - |
| `custUniqueId` | `string` | Required | - |
| `amountInUsd` | `number` | Required | - |
| `merchantRef` | `string` | Required | - |
| `instruction` | `string \| null` | Required | - |
| `merchantId` | `string \| null` | Required | - |
| `usePrivateKey` | `string \| null` | Required | - |
| `merchantName` | `string \| null` | Required | - |
| `agentId` | `number` | Required | - |
| `parentId` | `number` | Required | - |
| `whiteId` | `number` | Required | - |
| `year` | `string \| null` | Required | - |
| `month` | `string \| null` | Required | - |
| `day` | `string \| null` | Required | - |
| `hour` | `number` | Required | - |
| `bankid` | `string \| null` | Required | - |
| `setCurr` | `string` | Required | - |
| `pspReference` | `string \| null` | Required | - |
| `bankmid` | `string \| null` | Required | - |
| `bankname` | `string \| null` | Required | - |
| `status` | `string` | Required | - |
| `statusHistory` | [`StatusHistory8[]`](../../doc/models/status-history-8.md) | Required | - |
| `viewedOn` | `string \| null` | Required | - |
| `currency` | `string` | Required | - |
| `actionStatus` | [`ActionStatus`](../../doc/models/action-status.md) | Required | - |
| `fxCurrency` | `string \| null` | Required | - |
| `fxAmount` | `string \| null` | Required | - |
| `referer` | `string \| null` | Required | - |
| `clientIp` | `string` | Required | - |
| `merchantIp` | `string` | Required | - |
| `transFees` | `string \| null` | Required | - |
| `mdr` | `string \| null` | Required | - |
| `ruleName` | `string` | Required | - |
| `cascadeNum` | `string \| null` | Required | - |
| `conversionRiskFactorApplied` | `string \| null` | Required | - |
| `feesDeducted` | `number` | Required | - |
| `signature` | `string \| null` | Required | - |
| `puId` | `string` | Required | - |
| `uId` | `number` | Required | - |
| `authKey` | `string` | Required | - |
| `currencyConversion` | `string \| null` | Required | - |
| `successCallback` | `string` | Required | - |
| `failureCallback` | `string` | Required | - |
| `successRedirect` | `string` | Required | - |
| `failureRedirect` | `string` | Required | - |
| `pendingRedirect` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CreatePayoutSuccess } from 'ps-apimatic-sdk';

const createPayoutSuccess: CreatePayoutSuccess = {
  type: 'Payout',
  payoutId: '69cd1236e36738557e988399',
  client: {
    type: 'PClientDetails',
    customerId: 'NA',
    email: 'gouridausa+2@gmail.com',
    phone: '+14378817874',
    fullName: 'Ashish Mistry',
    dateOfBirth: 'date_of_birth0',
    streetAddress: 'test test',
    country: 'CA',
    city: 'Torronto',
    zipCode: '234567',
    documentId: 'documentId6',
    documentType: 'documentType8',
    speiClabe: 'spei_clabe0',
    speiDebitCard: 'spei_debitCard2',
    speiMobileNo: 'spei_mobileNo8',
    stateCode: 'CT',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  updatedOn: 1775047222,
  payoutMethod: 'PAYOUT-INTERAC-ETRANSFER',
  beneficiaryDetail: 'beneficiaryDetail4',
  amountUnit: 'MAJOR',
  amount: 5,
  errorMsg: 'paid',
  issued: '2026-04-01',
  responseMsg: 'responseMsg2',
  purpose: 'Transfer Interac',
  createdOn: 1775047222,
  custUniqueId: 'ashishm.21190@gmail.com',
  amountInUsd: 3.6,
  merchantRef: '69cd1236e36738557e988399',
  instruction: 'instruction4',
  merchantId: 'merchant_id4',
  usePrivateKey: 'usePrivateKey8',
  merchantName: 'merchantName4',
  agentId: 0,
  parentId: 0,
  whiteId: 0,
  year: 'year6',
  month: 'month4',
  day: 'day4',
  hour: 12,
  bankid: 'bankid0',
  setCurr: 'CAD',
  pspReference: 'pspReference6',
  bankmid: 'bankmid4',
  bankname: 'bankname2',
  status: 'paid',
  statusHistory: [
    {
      type: 'Status',
      status: 'created',
      timestamp: 1775047222,
      updatedBy: 'updatedBy8',
      paidReason: 'paidReason4',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      type: 'Status',
      status: 'paid',
      timestamp: 1775047239,
      updatedBy: 'updatedBy8',
      paidReason: 'paidReason4',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  viewedOn: 'viewedOn4',
  currency: 'CAD',
  actionStatus: {
    type: 'ApiError',
    message: 'message6',
    actualMessage: 'actualMessage6',
    merchantName: 'merchantName6',
    code: 'success',
    status: 'paid',
    callbackUrl: 'callback_url6',
    method: 'method0',
    beneficiaryId: 'beneficiaryId6',
    profileId: 'profileId6',
    payInBankDetail: 'payInBankDetail6',
    pixPayload: 'pix_payload4',
    payInDetails: {
      type: 'PayInDetail',
      name: 'INTERAC E-TRANSFER',
      emailAddress: 'ashishm.21190@gmail.com',
      secretQa: 'q691236367385579883992851',
      secretAnswer: 'a691236367385579883992851',
      referenceNumber: 'reference_number8',
      paymentMethod: 'payment_method8',
      transactionExpiry: 'transaction_expiry2',
      qrCode: 'qrCode0',
      gpayUri: 'gpayUri2',
      phonepeUri: 'phonepeUri8',
      paytmUri: 'paytmUri4',
      intentUri: 'intentUri8',
      generatedLink: 'generatedLink2',
      instruction: 'instruction2',
      paymentUrl: 'paymentUrl2',
      script: 'script2',
      clabe: 'clabe2',
      beneficiary: 'beneficiary0',
      amount: 'amount4',
      linkExpiresOn: 'linkExpiresOn0',
      cardExpiresOn: 'cardExpiresOn2',
      subStatus: 'subStatus8',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    balance: 'balance0',
    vab: 'vab6',
    authKey: 'authKey8',
    methodExecutionTime: 'methodExecutionTime8',
    password: 'password0',
    salt: 'salt8',
    nextCall: 'nextCall2',
    nextUrl: 'nextURL8',
    descriptor: 'descriptor8',
    currentTime: 1775047239,
    custVerificationString: 'custVerificationString0',
    instructions: 'instructions6',
    trustScore: 'trustScore0',
    trustLevel: 'trustLevel4',
    noOfCustHits: 'no_Of_Cust_Hits0',
    noOfHits: 'no_Of_Hits2',
    referer: 'referer8',
    clientIp: 'clientIp0',
    merchantIp: 'merchantIp4',
    isS2S: 'isS2s6',
    otp: 'otp4',
    userDeviceId: 'userDeviceId8',
    isAllowed: 'isAllowed4',
    logoUrl: 'logo_url4',
    transactionExpireInMin: 'transactionExpireInMin2',
    mandateReferenceId: 'mandateReferenceId8',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  fxCurrency: 'fx_Currency2',
  fxAmount: 'fx_Amount4',
  referer: 'referer6',
  clientIp: '95.217.22.130',
  merchantIp: '95.217.22.130',
  transFees: 'transFees6',
  mdr: 'MDR8',
  ruleName: 'Rule_Not_Applied',
  cascadeNum: 'cascade_Num6',
  conversionRiskFactorApplied: 'conversionRiskFactorApplied4',
  feesDeducted: 0,
  signature: 'signature2',
  puId: '',
  uId: 0,
  authKey: '',
  currencyConversion: 'currency_conversion2',
  successCallback: '',
  failureCallback: '',
  successRedirect: 'https://success.com',
  failureRedirect: 'https://failure.com',
  pendingRedirect: 'https://pending.com',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

