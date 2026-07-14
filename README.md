# 東尼 UI／網站設計參考庫

這個 Repository 用來保存可重複使用的 UI 設計來源、中文拆解與 AI 協作流程。

它不是素材下載站，也不是網站複製倉庫。核心用途是：

- 看懂每個設計來源適合解決什麼問題
- 知道什麼階段該用什麼工具
- 把參考網站轉成 AI 能執行的設計規格
- 避免直接叫 Codex 寫 UI，最後只得到模板感很重的頁面
- 保存之後可以交給 Codex、ChatGPT 或其他 coding agent 的中文操作說明

## 目前文件

1. [`docs/UI-REFERENCE-LIBRARY.zh-TW.md`](docs/UI-REFERENCE-LIBRARY.zh-TW.md)
   - 五個來源逐一拆解
   - 用途、限制、風險與中文使用方式
   - 什麼時候該用、什麼時候不要用

2. [`docs/TONY-UI-WORKFLOW.zh-TW.md`](docs/TONY-UI-WORKFLOW.zh-TW.md)
   - 東尼版 UI 工作流
   - 從需求盤點、概念圖、DESIGN.md、實作、動效到上線檢查
   - 可直接交給 Codex 的提示詞模板

## 收錄來源

- GitHub `website-clone` Topic
- VoltAgent `awesome-design-md`
- Level UP 升級志：Codex 品牌網站參考圖流程
- Emil Kowalski：AI Skills for Design Engineers
- HackMD：AI UI 設計五階段工作流

## 使用原則

- 參考結構、節奏、設計規則，不一比一複製品牌網站。
- 不使用對方 Logo、商標、專屬插圖或未授權素材。
- 不把整張設計稿直接當網頁背景。
- 文字、按鈕、導覽、表格與互動元件應保留為 HTML／CSS／元件程式碼。
- 不執行來源不明的網站複製、爬蟲或釣魚工具。
- 正式開發前先固定一份自己的 `DESIGN.md`。

最後整理日期：2026-07-15
