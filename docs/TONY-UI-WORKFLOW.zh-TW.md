# 東尼版 AI UI 工作流

版本：2026-07-15  
適用：東尼多元宇宙、Error 404、作品集、工具網站、私人工作中控台。

---

## 一、最高原則

不要再用這種方式開始：

```text
幫我把這頁做得有質感一點。
```

改成：

```text
先盤點資訊架構。
再做 2～3 個可看的 concept。
選定後整理 DESIGN.md。
最後才進入程式實作。
```

---

## 二、標準流程

### Step 0｜保存目前版本

先保存：

- Screenshot
- Git commit
- Git tag
- 目前路由
- 現有功能與權限測試

提示詞：

```text
請先保存改版前版本。
不要修改 UI。

建立桌機與手機截圖，記錄目前 commit、路由、已知問題與驗收結果。
建立改版前 Git tag。
完成後停下來回報。
```

### Step 1｜內容與資訊架構盤點

回答：

- 這頁是給誰用？
- 使用者打開後第一件事是什麼？
- 哪三件資訊最重要？
- 哪些是公開、匿名、私人？
- 哪些只是入口？
- 哪些是真正資料？
- 哪些功能目前不存在？

工作台建議骨架：

```text
東尼多元宇宙                    Ctrl／⌘K
------------------------------------------------
側欄              今天
總覽              最重要的 3 件事
案件
專案              正在運行／等待處理
證據庫
入口              專案動態
------------------------------------------------
Gmail
Drive
GitHub
```

### Step 2｜產生 2～3 個視覺 Concept

限制：

- 假資料
- 不接 API
- 不改登入
- 不改路由
- 不動真實資料
- 桌機＋手機
- 每個 concept 說明優缺點

提示詞：

```text
請先不要修改正式頁面，也不要寫 production code。

根據以下產品 brief，建立 3 個完整 UI concept：
A. 沉穩產品工作台
B. 編輯感內容工作台
C. 快速操作型 command workspace

每個 concept 都要包含：
- Dashboard
- Cases Registry
- Projects／Links
- 桌機 1440px
- 手機 390px
- 色彩
- 字體層級
- 側欄
- 列表／卡片密度
- 狀態
- 空狀態
- 優點
- 風險

完成後只提供 preview 與差異，不自行選定版本。
```

### Step 3｜建立自有 DESIGN.md

參考來源可以混合角色，但不能拼貼 UI。

東尼多元宇宙建議：

- Linear：資訊架構
- WIRED：內容人格
- Raycast：操作回饋

提示詞：

```text
根據我選定的 concept，建立本專案自己的 DESIGN.md。

不要使用參考品牌名稱當作最終設計描述。
請轉成自己的 tokens、規則與元件語言。

至少包含：
- 產品氣質
- 色彩
- 字體
- 間距
- grid
- 側欄
- header
- command palette
- card
- registry
- inspector
- table
- status
- button
- form
- empty／loading／error
- responsive
- motion
- accessibility
- 禁止事項
```

### Step 4｜工程實作

順序：

1. 修路由與資料映射。
2. 保留功能與權限。
3. 建立 tokens。
4. 改 shell／sidebar／header。
5. 改單頁。
6. 加 responsive。
7. 跑測試。
8. 每頁 screenshot 比對。

提示詞：

```text
請依 DESIGN.md 實作選定 concept。

強制保留：
- Cloudflare Access
- Owner guard
- 401／403／200
- 公開／私人資料邊界
- 現有 API
- 路由語意
- 隱私測試

不要：
- 先把資料送前端再隱藏
- 把 Owner Email 寫進 bundle
- 把私人資料放進公開 HTML
- 為了 UI 重寫 auth
- 改動不相關專案
```

### Step 5｜視覺 QA

檢查：

- 是否還像 AI 模板
- 是否字太小
- 是否大量空白
- 是否框線太多
- 是否層級不足
- 是否所有東西都變卡片
- 是否狀態難掃描
- 是否桌機空間浪費
- 是否手機只是硬縮

提示詞：

```text
請做 UI audit，先不要修改。
用 P0／P1／P2 排序列出：
- 資訊架構
- 層級
- 字體
- 間距
- 對齊
- 色彩
- 元件一致性
- 空狀態
- RWD
- AI 模板感

每個問題要包含具體位置與修改方向。
```

### Step 6｜動效

只加必要動效：

- Command Palette
- Sidebar
- Inspector
- Toast
- 狀態變化
- modal／popover

提示詞：

```text
請使用 emil-design-eng，只加入有功能理由的動效。
所有動畫需支援 prefers-reduced-motion。
禁止大面積 parallax、長時間 page transition 與無意義彈跳。
```

### Step 7｜上線前驗收

技術：

- lint
- typecheck
- tests
- build
- privacy
- auth
- responsive
- no overflow

UX：

- 鍵盤
- focus
- screen reader
- 對比
- loading
- error
- empty
- 404
- mobile

安全：

- 公開頁無私人資料
- Owner Email 不在 bundle
- internalNotes 不在 HTML
- private case 公開路由為 404
- 未登入內部 API 不可讀
- 非 Owner 被拒絕
- Owner 可進入

---

## 三、不同產品該用哪種流程

### 公開品牌網站

重點：

- Briefing
- 參考圖
- 編輯感
- 品牌記憶
- 圖片素材拆解
- SEO／RWD

### 私人工作台

重點：

- 資訊架構
- 掃描效率
- 狀態
- 列表
- 搜尋
- 快捷入口
- 長時間使用
- 權限與隱私

### 工具型產品

重點：

- 任務流程
- 表單
- 錯誤狀態
- 空狀態
- 本地／雲端資料說明
- onboarding
- feedback

---

## 四、東尼目前的 UI 禁止事項

- 公家機關內網感
- Excel 放大版
- 超小字
- 超大空白
- 所有內容都有框
- 每個資訊都做成卡片
- Hero＋三卡＋CTA 的預設模板
- 黑金成功學
- 過度玻璃擬態
- 霓虹 AI 官網
- 為了炫技犧牲可讀性
- 動畫比內容更搶眼
- 公開與私人資料混在一起

---

## 五、每次開工前交給 Codex 的短版

```text
先讀：
1. docs/UI-REFERENCE-LIBRARY.zh-TW.md
2. docs/TONY-UI-WORKFLOW.zh-TW.md
3. 專案自己的 DESIGN.md

先判斷目前處於：
概念探索／設計決策／DESIGN.md／實作／QA／動效／上線檢查。

不要跳階段。
不要在未選定 concept 前直接改正式 UI。
不要破壞登入、權限、資料邊界與既有測試。
```
