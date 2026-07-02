
# Action Status

*This model accepts additional fields of type unknown.*

## Structure

`ActionStatus`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `type` | `string` | Required | - |
| `message` | `string \| null` | Required | - |
| `actualMessage` | `string \| null` | Required | - |
| `merchantName` | `string \| null` | Required | - |
| `code` | `string` | Required | - |
| `status` | `string` | Required | - |
| `callbackUrl` | `string \| null` | Required | - |
| `method` | `string \| null` | Required | - |
| `beneficiaryId` | `string \| null` | Required | - |
| `profileId` | `string \| null` | Required | - |
| `payInBankDetail` | `string \| null` | Required | - |
| `pixPayload` | `string \| null` | Required | - |
| `payInDetails` | [`PayInDetails2`](../../doc/models/pay-in-details-2.md) | Required | - |
| `balance` | `string \| null` | Required | - |
| `vab` | `string \| null` | Required | - |
| `authKey` | `string \| null` | Required | - |
| `methodExecutionTime` | `string \| null` | Required | - |
| `password` | `string \| null` | Required | - |
| `salt` | `string \| null` | Required | - |
| `nextCall` | `string \| null` | Required | - |
| `nextUrl` | `string \| null` | Required | - |
| `descriptor` | `string \| null` | Required | - |
| `currentTime` | `number` | Required | - |
| `custVerificationString` | `string \| null` | Required | - |
| `instructions` | `string \| null` | Required | - |
| `trustScore` | `string \| null` | Required | - |
| `trustLevel` | `string \| null` | Required | - |
| `noOfCustHits` | `string \| null` | Required | - |
| `noOfHits` | `string \| null` | Required | - |
| `referer` | `string \| null` | Required | - |
| `clientIp` | `string \| null` | Required | - |
| `merchantIp` | `string \| null` | Required | - |
| `isS2S` | `string \| null` | Required | - |
| `otp` | `string \| null` | Required | - |
| `userDeviceId` | `string \| null` | Required | - |
| `isAllowed` | `string \| null` | Required | - |
| `logoUrl` | `string \| null` | Required | - |
| `transactionExpireInMin` | `string \| null` | Required | - |
| `mandateReferenceId` | `string \| null` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ActionStatus } from 'ps-apimatic-sdk';

const actionStatus: ActionStatus = {
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
};
```

