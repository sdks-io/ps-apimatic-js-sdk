
# Optional Input

*This model accepts additional fields of type unknown.*

## Structure

`OptionalInput`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `lastBets` | `string \| null` | Required | - |
| `lastWins` | `string` | Required | - |
| `totalBonuses` | `string` | Required | - |
| `lastRealBets` | `string` | Required | - |
| `lastRealWins` | `string` | Required | - |
| `totalDeposits` | `string` | Required | - |
| `lastBonusBets` | `string` | Required | - |
| `lastBonusWins` | `string` | Required | - |
| `averageRealBet` | `string` | Required | - |
| `lastBetsAmount` | `string` | Required | - |
| `lastWinsAmount` | `string` | Required | - |
| `averageBonusBet` | `string` | Required | - |
| `bonusToDeposits` | `string` | Required | - |
| `lastDepositDate` | `string` | Required | - |
| `totalWithdrawals` | `string` | Required | - |
| `isPhoneConfirmed` | `string` | Required | - |
| `moneyInMoneyOut` | `string` | Required | - |
| `lastDepositAmount` | `string` | Required | - |
| `lastFreespinsDate` | `string` | Required | - |
| `lastFreespinsName` | `string` | Required | - |
| `lastFreeBonusDate` | `string` | Required | - |
| `lastFreeBonusName` | `string` | Required | - |
| `totalBonusesAmount` | `string` | Required | - |
| `lastFreespinsAmount` | `string` | Required | - |
| `lastFreespinsStatus` | `string` | Required | - |
| `lastRealBetsAmount` | `string` | Required | - |
| `lastRealWinsAmount` | `string` | Required | - |
| `totalDepositsAmount` | `string` | Required | - |
| `lastBonusBetsAmount` | `string` | Required | - |
| `lastBonusWinsAmount` | `string` | Required | - |
| `lastFreeBonusAmount` | `string` | Required | - |
| `lastFreeBonusStatus` | `string` | Required | - |
| `lastDepositBonusDate` | `string` | Required | - |
| `lastDepositBonusName` | `string` | Required | - |
| `lastFreespinsCurrency` | `string` | Required | - |
| `lastFreespinsWagering` | `string` | Required | - |
| `withdrawalsToDeposits` | `string` | Required | - |
| `lastFreeBonusCurrency` | `string` | Required | - |
| `lastFreeBonusWagering` | `string` | Required | - |
| `totalWithdrawalsAmount` | `string` | Required | - |
| `withdrawalEwalletEmail` | `string` | Required | - |
| `lastDepositBonusAmount` | `string` | Required | - |
| `lastDepositBonusStatus` | `string` | Required | - |
| `lastDepositBonusCurrency` | `string` | Required | - |
| `lastDepositBonusWagering` | `string` | Required | - |
| `session` | `string` | Required | - |
| `paymentMode` | `string` | Required | - |
| `cardFullname` | `string` | Required | - |
| `cardBin` | `string` | Required | - |
| `cardHash` | `string` | Required | - |
| `cardLast` | `string` | Required | - |
| `cardExpire` | `string` | Required | - |
| `avsResult` | `string` | Required | - |
| `cvvResult` | `string` | Required | - |
| `scaMethod` | `string` | Required | - |
| `userBankAccount` | `string` | Required | - |
| `userBankName` | `string` | Required | - |
| `userBalance` | `string` | Required | - |
| `userVerificationLevel` | `string` | Required | - |
| `status3D` | `string` | Required | - |
| `regulation` | `string` | Required | - |
| `paymentProvider` | `string` | Required | - |
| `phoneNumber` | `string` | Required | - |
| `transactionType` | `string` | Required | - |
| `transactionAmount` | `string` | Required | - |
| `transactionCurrency` | `string` | Required | - |
| `merchantId` | `string` | Required | - |
| `detailsUrl` | `string` | Required | - |
| `name` | `string` | Required | - |
| `personType` | `string` | Required | - |
| `gender` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { OptionalInput } from 'ps-apimatic-sdk';

const optionalInput: OptionalInput = {
  lastBets: 'last_bets2',
  lastWins: '',
  totalBonuses: '',
  lastRealBets: '',
  lastRealWins: '',
  totalDeposits: '',
  lastBonusBets: '',
  lastBonusWins: '',
  averageRealBet: '',
  lastBetsAmount: '',
  lastWinsAmount: '',
  averageBonusBet: '',
  bonusToDeposits: '',
  lastDepositDate: '',
  totalWithdrawals: '',
  isPhoneConfirmed: '',
  moneyInMoneyOut: '',
  lastDepositAmount: '',
  lastFreespinsDate: '',
  lastFreespinsName: '',
  lastFreeBonusDate: '',
  lastFreeBonusName: '',
  totalBonusesAmount: '',
  lastFreespinsAmount: '',
  lastFreespinsStatus: '',
  lastRealBetsAmount: '',
  lastRealWinsAmount: '',
  totalDepositsAmount: '',
  lastBonusBetsAmount: '',
  lastBonusWinsAmount: '',
  lastFreeBonusAmount: '',
  lastFreeBonusStatus: '',
  lastDepositBonusDate: '',
  lastDepositBonusName: '',
  lastFreespinsCurrency: '',
  lastFreespinsWagering: '',
  withdrawalsToDeposits: '',
  lastFreeBonusCurrency: '',
  lastFreeBonusWagering: '',
  totalWithdrawalsAmount: '',
  withdrawalEwalletEmail: '',
  lastDepositBonusAmount: '',
  lastDepositBonusStatus: '',
  lastDepositBonusCurrency: '',
  lastDepositBonusWagering: '',
  session: '',
  paymentMode: '',
  cardFullname: '',
  cardBin: '',
  cardHash: '',
  cardLast: '',
  cardExpire: '',
  avsResult: '',
  cvvResult: '',
  scaMethod: '',
  userBankAccount: '',
  userBankName: '',
  userBalance: '',
  userVerificationLevel: '',
  status3D: '',
  regulation: '',
  paymentProvider: '',
  phoneNumber: '',
  transactionType: '',
  transactionAmount: '',
  transactionCurrency: '',
  merchantId: '',
  detailsUrl: '',
  name: '',
  personType: '',
  gender: '',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

