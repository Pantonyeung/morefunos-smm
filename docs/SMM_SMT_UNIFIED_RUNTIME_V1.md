# More Fun／磨飯 SMM × SMT 統一 Runtime 規格 V1

狀態：CURRENT / LOCKED
日期：2026-07-24

## 1. 產品定義

SMM 與 SMT 從此視為同一套 More Fun Staff POS／營運系統的兩個介面層：

- SMT：Sunmi T2S 1280×800 橫屏收銀機／正式營運主機介面。
- SMM：iPhone／Android 手機營運介面。

兩者不是兩套獨立商業系統，不應各自維護商品、價格、套餐、訂單狀態或商業規則。

## 2. 單一資料權威

正式資料逐步接入後，SMM 與 SMT 必須共同讀取同一套權威資料來源。

正式商品資料權威：Admin 後台。

包括：
- 分類
- 商品
- 價格
- 套餐／組合
- 選項
- 加減價
- 排序
- 啟用／停用
- 售罄／供應狀態規則

在 Admin 正式資料接入前，可使用 MOCK／TEST 假資料驗證 UI 與操作；假資料不得升格為正式餐牌。

## 3. 共用規則

SMM 與 SMT 必須共用：
- 商品與套餐規則
- Required／Pool／Link Up
- Cart／Order／Payment／Refund 狀態模型
- 訂單身份及版本
- 堂食 Session 規則
- 售罄規則
- 報表資料定義
- Print Job Contract
- Offline／Outbox／Sync Contract

不得在 SMM 或 SMT 前端各自硬編另一套規則。

## 4. UI 分離

資料與功能統一，不代表介面必須相同。

SMT：
- 原生 1280×800
- 高資訊密度
- 收銀機橫屏
- 高峰快速操作

SMM：
- 手機直屏優先
- 卡片／逐步流程
- 手機安全區
- 不直接縮小 SMT 介面

## 5. 打印硬件邊界

SMM 可以建立、查看、重試、取消、改送 Print Job，但不直接連接實體打印機。

SMT Android Host／正式主機仍負責：
- 實體打印連線
- 靜默打印
- 回傳真實打印結果

## 6. 開發分支

SMM 功能來源分支：`feat/smm-mobile-v1`

SMM × SMT 手機視覺驗收工作分支：`agent/smm-smt-unified-preview`

SMT 1280×800 原生重建工作分支：`agent/smt-1280x800-native-rebuild`

## 7. 手機視覺驗收入口

`index.html` 為統一驗收首頁：
- SMM 手機版：`smm.html`
- SMT 收銀機版：`smt-preview.html`

SMT 手機驗收工具以黑背景＋黃色 1280×800 邊框顯示。

「完整縮放」只發生在驗收工具外層，不得改變 SMT iframe 內部的 1280×800 viewport；「100% 原尺寸」用作拖動檢查 overflow、遮擋、錯位及觸控問題。

## 8. 禁止

- 禁止 SMM 與 SMT 各自維護正式商品資料。
- 禁止將 SMM 假資料當正式資料。
- 禁止用舊 SMT 商品／價格覆蓋 Admin。
- 禁止將 SMT 1280×800 介面直接縮成 SMM 正式 UI。
- 禁止因手機驗收外框使用縮放，而在 SMT 正式產品內使用整頁 scale。
