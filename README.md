# More Fun SMM

磨飯 SMM（Staff Mobile Management）手機營運端。

## Current baseline

- Source SMT repo: `Pantonyeung/morefunos-smt`
- Source SMT branch: `feat/smt-order-page-v1`
- Source SMT package/version: `order-v1-31`
- SMM development branch: `feat/smm-mobile-v1`
- Current UI version: `smm-v1-02-ui-complete`
- UI lock: `docs/SMM_UI_LOCK_V1.md`

## Implemented V1 screens

1. 登入
2. 工作台
3. 點單／商品分類
4. 商品詳情／配置
5. 購物車
6. 確認訂單／付款方式
7. 訂單建立成功
8. 訂單列表
9. 訂單詳情
10. 堂食枱位管理
11. 售罄管理
12. 報表總覽
13. 打印工作管理
14. 更多功能

## Implemented interactions

- 登入及登出
- 商品分類與售罄狀態
- 商品配置、加配、數量及購物車
- 訂單來源及付款方式
- 訂單列表篩選及詳情
- 堂食枱位狀態切換
- 售罄開關
- PWA 離線快取更新

## Integration boundary

目前為可操作 UI／流程原型，使用示範資料。正式營運前仍需接駁：

- Staff／Sync API 登入與裝置綁定
- 正式商品、定價及商業規則
- 訂單建立／更新／取消 API
- 堂食、付款、售罄及報表 API
- SMT print-job queue 與實際打印結果回傳

SMM 不直接連接實體打印機。SMM 建立 print job，由 SMT Android host 靜默執行並回傳結果。

## Repository rule

Do not modify the SMT source repository from this project. Reuse its data contracts and business logic only after documenting the extraction boundary.
