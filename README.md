# More Fun SMM｜Migration Source

> 狀態：MIGRATION SOURCE / HISTORICAL ARCHIVE  
> 生效日期：2026-07-29  
> 正式 Authority：`Pantonyeung/morefunos-smt`  
> 最高決策：SMT Decision D-053

## Product decision

SMM 不再作獨立 Application、獨立 Runtime 或獨立業務系統發展。

正式產品只保留一個 SMT Application，提供：

- `register`：收銀機／大屏 UI Profile
- `mobile`：原 SMM 手機 UI Profile

兩個 Profile 必須共用同一套：

- Domain
- Data Model
- Business Rule
- Cart
- Pricing
- Checkout
- Order
- Payment
- Dine
- Permission
- Sync
- Recovery
- API Contract
- Audit
- Print Job Contract

## Printing boundary

Mobile Profile 可以建立、查看、重試及取消打印工作，但不得直接連接實體打印機。

正式打印流程：

`Mobile UI → Shared Print Domain → Print Job API → SMT Android Host → Printer → Actual Result Callback`

排隊成功不等於實體打印成功；只有 Android Host 回傳設備級結果後，才可標示 `success`。

## Repository rule

本 repository 即日起只可作：

- 舊手機 UI 盤點
- PWA／mobile lifecycle 遷移來源
- 可重用 mobile interaction 與測試來源
- 歷史比對及回歸參考

禁止：

- 新增獨立核心功能
- 建立第二套 Domain／API／資料模型
- 繼續以舊 SMT baseline 作正式 Runtime
- 直接在本 repo 實作新 Order／Payment／Print Core

所有正式遷移結果必須寫入 `Pantonyeung/morefunos-smt`。

## Historical baseline

以下只保留作歷史參考，不代表現行 Authority：

- Source SMT branch: `feat/smt-order-page-v1`
- Source SMT package/version: `order-v1-31`
- SMM development branch: `feat/smm-mobile-v1`
- Initial SMM version: `smm-v1-01`
