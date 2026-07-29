# More FunOS｜四端閉環總控權威入口

> 狀態：CURRENT / REDIRECT / SMM INDEPENDENT CORE SUPERSEDED
> 正式總控 Authority：`Pantonyeung/morefunos` → `main` → `MOREFUNOS_MASTER_CONTROL_AUTHORITY.md`
> 更新：2026-07-29 19:49 HKT

SMM 不再作獨立系統發展。

SMM 已正式合併為 SMT Mobile UI，與 SMT Register UI 共用同一套 Domain、State、Business Rule、Cart、Pricing、Checkout、Order、Payment、Sync、Permission、Audit、Recovery、API Contract。

本 repo 後續只可作歷史參考、遷移來源或受控抽取；不得再建立第二套 SMM 核心。

SMT Mobile 只建立 Print Job／Command，不直接控制實體打印機；打印交由 SMT Android Host 執行並回傳結果。
