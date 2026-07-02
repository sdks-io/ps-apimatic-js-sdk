
# Check Transaction Allowed Request

*This model accepts additional fields of type unknown.*

## Structure

`CheckTransactionAllowedRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requiredinput` | [`Requiredinput`](../../doc/models/requiredinput.md) | Required | - |
| `optionalInput` | [`OptionalInput`](../../doc/models/optional-input.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CheckTransactionAllowedRequest } from 'ps-apimatic-sdk';

const checkTransactionAllowedRequest: CheckTransactionAllowedRequest = {
  requiredinput: {
    ip: '111.11.11.11',
    email: 'test@gmail.com',
    url: 'https://www.asos.com/',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  optionalInput: {
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
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

