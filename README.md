# More Fun SMM｜SUPERSEDED Migration Source

> **Authority Level：C／E**  
> **Status：SUPERSEDED AS INDEPENDENT CORE／REFERENCE ONLY**  
> 正式 Authority：`Pantonyeung/morefunos` 中央 Master Authority＋Current Registry；正式實作 repo：`Pantonyeung/morefunos-smt`。

## 開工前必讀

任何 AI／Codex／Work 必須先讀：

1. `Pantonyeung/morefunos/MOREFUNOS_MASTER_CONTROL_AUTHORITY.md`
2. `MOREFUNOS_DEVELOPMENT_MUST_READ.md`
3. `MOREFUNOS_CURRENT_DEVELOPMENT_REGISTRY.md`
4. `MOREFUNOS_DOCUMENT_AUTHORITY_CLASSIFICATION.md`
5. `MOREFUNOS_LEGACY_REFERENCE_INVENTORY.md`
6. 本 repo `MOREFUNOS_AUTHORITY_BOUNDARY.md`

## Product decision

SMM 不再作獨立 Application、Runtime、Business Core 或部署 Authority。

正式產品只保留一個 SMT Application：

- `register`：收銀機／大屏 UI Profile；
- `mobile`：原 SMM 手機／平板 UI Profile。

兩個 Profile 共用同一 Domain、Data Model、Business Rule、Cart、Pricing、Checkout、Order、Payment、Dine、Permission、Sync、Recovery、API Contract、Audit 及 Print Job Contract。

## Repository allowed use

本 repository 只可作：

- 舊手機 UI／Interaction 盤點；
- PWA／mobile lifecycle migration source；
- 可重用測試及裝置行為來源；
- 歷史比對、回歸及踩坑參考。

禁止：

- 新增獨立核心功能；
- 建立第二套 Domain／API／Data Model／Auth／Firebase／Sync；
- 直接實作新 Order／Pricing／Payment／Print Core；
- 將舊 branch、README、handoff、WORK03、Apps Script 或 Google Sheet 當 Current Authority；
- 將本 repo 重新接回獨立 Cloudflare production deployment。

所有正式遷移結果必須寫入 `Pantonyeung/morefunos-smt`，並經 Current Registry、active branch／PR／head evidence 驗證。

## Printing boundary

Mobile Profile 可以建立、查看、重試及取消 Print Job，但不得直接連接實體打印機。

```text
Mobile UI → Shared Print Domain → Print Job API → SMT Android Host → Printer → Actual Result Callback
```

Queue／API success 不等於實體打印 success。

## Historical baseline

以下只保留歷史識別，不代表現行 Authority：

- `feat/smt-order-page-v1`
- `order-v1-31`
- `feat/smm-mobile-v1`
- `smm-v1-01`
- 所有 SMM 舊 WORK／handoff／QA／deployment 記錄
