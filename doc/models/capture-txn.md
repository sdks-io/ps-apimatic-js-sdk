
# Capture Txn

*This model accepts additional fields of type unknown.*

## Structure

`CaptureTxn`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `captureId` | `string` | Required | - |
| `purchaseId` | `string` | Required | - |
| `amount` | `number` | Required | - |
| `fxAmount` | `number` | Required | - |
| `status` | `string` | Required | - |
| `pspReference` | `string \| null` | Required | - |
| `merchantReference` | `string` | Required | - |
| `createdAt` | `number` | Required | - |
| `updatedAt` | `number` | Required | - |
| `whiteId` | `number` | Required | - |
| `fxCurrency` | `string` | Required | - |
| `bankMid` | `string` | Required | - |
| `isTest` | `boolean` | Required | - |
| `currency` | `string` | Required | - |
| `amountInUsd` | `number` | Required | - |
| `merchantName` | `string` | Required | - |
| `bankName` | `string` | Required | - |
| `bankId` | `string` | Required | - |
| `trxMethod` | `string` | Required | - |
| `rollingReserve` | `number` | Required | - |
| `transFees` | `number` | Required | - |
| `mdr` | `number` | Required | - |
| `isSettlementPending` | `number` | Required | - |
| `parentId` | `number` | Required | - |
| `transSettlementId` | `string \| null` | Required | - |
| `errorSettlementId` | `string \| null` | Required | - |
| `merchantId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CaptureTxn } from 'ps-apimatic-sdk';

const captureTxn: CaptureTxn = {
  captureId: '41e31f9f-1e98-4f4d-b48c-7d1ed488fc3f',
  purchaseId: '69cd361053d7b783ebf7324d',
  amount: 10,
  fxAmount: 10,
  status: 'PAID',
  pspReference: 'pspReference8',
  merchantReference: '64534345',
  createdAt: 1775056447,
  updatedAt: 1775056447,
  whiteId: 0,
  fxCurrency: 'EUR',
  bankMid: 'payneticsexternal3ds',
  isTest: false,
  currency: 'EUR',
  amountInUsd: 11.85,
  merchantName: 'KailashMerchant',
  bankName: 'paynatics-aft_',
  bankId: '532',
  trxMethod: 'CARDS',
  rollingReserve: 0,
  transFees: 0,
  mdr: 0,
  isSettlementPending: 0,
  parentId: 0,
  transSettlementId: 'transSettlementId6',
  errorSettlementId: 'errorSettlementId2',
  merchantId: '589',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

