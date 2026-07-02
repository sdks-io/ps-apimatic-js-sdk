
# Pay in Details 2

*This model accepts additional fields of type unknown.*

## Structure

`PayInDetails2`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `type` | `string` | Required | - |
| `name` | `string` | Required | - |
| `emailAddress` | `string` | Required | - |
| `secretQa` | `string` | Required | - |
| `secretAnswer` | `string` | Required | - |
| `referenceNumber` | `string \| null` | Required | - |
| `paymentMethod` | `string \| null` | Required | - |
| `transactionExpiry` | `string \| null` | Required | - |
| `qrCode` | `string \| null` | Required | - |
| `gpayUri` | `string \| null` | Required | - |
| `phonepeUri` | `string \| null` | Required | - |
| `paytmUri` | `string \| null` | Required | - |
| `intentUri` | `string \| null` | Required | - |
| `generatedLink` | `string \| null` | Required | - |
| `instruction` | `string \| null` | Required | - |
| `paymentUrl` | `string \| null` | Required | - |
| `script` | `string \| null` | Required | - |
| `clabe` | `string \| null` | Required | - |
| `beneficiary` | `string \| null` | Required | - |
| `amount` | `string \| null` | Required | - |
| `linkExpiresOn` | `string \| null` | Required | - |
| `cardExpiresOn` | `string \| null` | Required | - |
| `subStatus` | `string \| null` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PayInDetails2 } from 'ps-apimatic-sdk';

const payInDetails2: PayInDetails2 = {
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
};
```

