# UI 設計來源拆解與中文使用說明

更新日期：2026-07-15  
用途：給東尼、Codex、ChatGPT 與其他 coding agent 使用的 UI 參考庫。

---

## 快速判斷表

| 來源 | 核心用途 | 適合階段 | 優先度 |
|---|---|---|---|
| GitHub `website-clone` Topic | 找網站重製、爬取、clone 範例 | 探索工具，不作設計標準 | 低 |
| `awesome-design-md` | 取得可被 AI 讀懂的品牌設計規則 | 選定視覺方向、建立 DESIGN.md | 最高 |
| Level UP Codex 參考圖流程 | 先做品牌 briefing 與參考圖，再實作 | 品牌網站、作品集、公開首頁 | 高 |
| Emil Kowalski Skill | 動效設計與動畫檢查 | UI 已完成後 | 高 |
| AI UI 五階段工作流 | 管理整個 UI 產製順序 | 從零到上線 | 最高 |

---

# 1. GitHub `website-clone` Topic

來源：  
https://github.com/topics/website-clone

## 它是什麼

GitHub 上標記為 `website-clone` 的公開 Repository 集合。內容混合：

- AI 網站 clone 工具
- 網站下載器與 crawler
- Tailwind／React 練習專案
- Amazon、Netflix、BBC 等仿站練習
- 部分資安、釣魚或滲透測試工具

## 真正用途

這個來源適合拿來：

1. 找「網站結構怎麼拆」的範例。
2. 觀察別人如何處理 RWD、導覽列、卡片、Hero、列表。
3. 找前端練習專案，理解某種 UI 的元件拆法。
4. 找網站 screenshot／HTML 分析／clone workflow 的工具線索。

## 不適合拿來做什麼

- 不要把排行榜第一名當成設計品質保證。
- 不要直接執行陌生 repo。
- 不要拿來複製別人的正式品牌網站。
- 不要把 clone 出來的網站當作品集成品。
- 不要使用帶有 phishing、credential capture、red-team 字樣的工具處理真實帳號或正式網域。

## 中文使用方式

### 想找「版面拆法」

1. 進入 Topic。
2. 優先看 HTML／CSS／TypeScript／React 類型。
3. 打開 demo 或 screenshot。
4. 只觀察：
   - 區塊順序
   - 導覽方式
   - 卡片密度
   - 手機版折疊
   - 元件命名與檔案結構
5. 不複製 Logo、文案、圖片、品牌元素。

### 可以交給 Codex 的提示詞

```text
請閱讀這個網站 clone 專案，但不要複製品牌內容。
只分析它的頁面結構、元件拆分、RWD 方式、導覽模式與可重用 UI 模式。
輸出：
1. 可借用的結構
2. 不應照抄的品牌元素
3. 對目前專案可用的元件清單
4. 資安或授權風險
先分析，不修改程式。
```

## 東尼目前的使用建議

優先度低。只在想研究某個特定頁面結構時使用。  
不要用它決定「東尼多元宇宙」的視覺風格。

---

# 2. VoltAgent `awesome-design-md`

來源：  
https://github.com/VoltAgent/awesome-design-md

## 它是什麼

收錄多個知名網站的 `DESIGN.md` 分析。重點不是下載網站，而是把網站的設計語言整理成 AI 能讀的 Markdown，例如：

- 色彩 tokens
- 字體層級
- 間距規則
- 卡片與按鈕
- 版面節奏
- 動效原則
- 應避免的設計方式

## 真正用途

1. 先選 1～3 個設計方向。
2. 讓 Codex 讀取來源的 DESIGN.md。
3. 抽取規則，不直接照抄畫面。
4. 合成自己的 DESIGN.md。
5. 讓後續新增頁面維持一致。

## 中文使用方式

### 第一步：先選「角色」，不要只選「好看」

例如：

- Linear：工作台骨架、資訊密度、狀態清單。
- WIRED：編輯感、大標題、內容品牌人格。
- Raycast：快速入口、Command Palette、操作回饋。
- Notion：溫暖、內容型、柔和表面。
- Vercel：黑白精準、工程感。
- Superhuman：高效率、鍵盤操作、深色高級感。

### 第二步：要求 AI 做「抽取」，不是「複製」

```text
請閱讀以下 DESIGN.md。
不要一比一複製原品牌，也不要使用其 Logo、商標、專屬字體或素材。

請只抽取：
- 資訊層級
- 色彩邏輯
- 字級比例
- 間距系統
- 元件密度
- 導覽模式
- 狀態呈現
- 動效原則
- 禁止事項

最後整合成目前產品自己的 DESIGN.md。
```

### 第三步：合成自有設計系統

自有 `DESIGN.md` 至少包含：

```text
品牌與產品定位
使用者情境
色彩 tokens
字體與字級
間距
頁面寬度
側欄
頂部列
卡片
列表／表格
Registry／Inspector
按鈕
標籤
表單
空狀態
錯誤狀態
Responsive
Motion
Accessibility
禁止事項
```

## 東尼目前的使用建議

核心組合：

- Linear：私人工作台骨架
- WIRED：Error 404 的內容人格
- Raycast：快速入口與操作手感

不要把三套 UI 拼貼；要把三者轉成一份自己的規則。

---

# 3. Level UP：Codex 品牌網站參考圖流程

來源：  
https://levelupdiary.com/blog/codex-brand-website-reference-image-workflow/

## 核心觀念

不要一開始就叫 AI 寫首頁。  
先把品牌方向變成一張可對齊的參考圖，讓人和 AI 都能具體判斷「像不像」。

## 四步流程

1. 整理網站內容與品牌 briefing。
2. 生成網頁參考圖。
3. 拆解參考圖，單獨生成必要素材。
4. 用前端工具把參考圖復刻成真實網頁。

## 為什麼有用

直接叫 AI 寫 code，常會得到：

- 通用 SaaS landing page
- Hero＋三張卡＋CTA
- 顏色合理但沒有記憶點
- 每個區塊都存在，但不像品牌

先看參考圖，可以先判斷：

- 整體像不像自己
- 資訊是不是太滿
- 色彩是否跑掉
- 手機版是否能成立
- 哪些內容要保留、刪除或調整

## 中文使用方式

### A. 先做 briefing

```text
請先不要設計、不要寫 code。
請根據我提供的品牌、內容、目標使用者與目前網站，整理成網站 briefing。

請包含：
1. 品牌定位
2. 目標使用者
3. 首頁資訊架構
4. 每個區塊的任務
5. 第一眼必須理解的事
6. 視覺方向
7. 色彩與字體傾向
8. 不要出現的風格
9. 必須保留的品牌元素
10. 手機版優先順序
```

### B. 再做 2～3 張參考圖

```text
請根據 briefing 產生三個完整 UI concept。
先不要寫程式碼。

每個 concept 都要包含：
- 首屏
- 主要區塊節奏
- 側欄／導覽
- 色彩
- 字體層級
- 卡片與列表
- 桌機版
- 手機版
- 適合情境
- 風險與缺點
```

### C. 拆 code 與圖片素材

應該用 HTML／CSS／元件實作：

- 文字
- 導覽列
- 按鈕
- CTA
- 表單
- 卡片
- 表格
- 文章資料
- 可互動元件

可以使用圖片素材：

- Hero 氛圍背景
- 紙張紋理
- 裝飾貼紙
- 特殊插圖
- 封面圖

適合 SVG：

- Logo
- icon
- 流程線
- 幾何裝飾

## 重要禁區

- 不把整張參考圖當背景。
- 不把文字烤進圖片。
- 手機版不直接裁桌機版背景。
- 不為了像參考圖而犧牲 SEO、RWD、可維護性與可存取性。

## 東尼目前的使用建議

適合：

- Error 404 公開首頁
- 公開作品案例頁
- 求職作品集公開版
- 品牌入口頁

私人工作台仍以產品資訊架構為主，不要做成過度藝術化 landing page。

---

# 4. Emil Kowalski Skill

來源：  
https://emilkowal.ski/skill

安裝指令：

```bash
npx skills add emilkowalski/skill
```

## 它是什麼

針對 UI 動效與 motion decision 的技能組。主要包含：

- `emil-design-eng`：協助建立動畫與做動效判斷。
- `review-animations`：檢查現有動畫品質。

## 真正用途

適合 UI 已經完成之後，用來處理：

- 頁面切換
- Modal／Popover 出現與離開
- hover 回饋
- Command Palette
- 卡片展開
- loading
- success／error feedback
- list reorder
- micro interaction

## 不適合拿來做什麼

- 不能救資訊架構錯誤。
- 不能救字級太小、畫面太空、層級混亂。
- 不要一開始就加大量動畫。
- 不要讓每個元素都彈跳。
- 不要用動畫掩蓋載入慢或操作不清楚。

## 中文使用方式

### 建立動效

```text
請使用 emil-design-eng。
目前版面與資訊架構已定稿，請只設計必要動效。

請逐項定義：
- 哪個元件要動
- 觸發條件
- 進場／離場
- duration
- easing
- 是否支援 reduced motion
- 動效存在的功能理由

不要加入純裝飾動畫。
```

### 動效 QA

```text
請使用 review-animations 檢查目前頁面。
請找出：
- 太慢
- 太多
- easing 不自然
- 進出場不對稱
- layout shift
- hover 過度
- reduced-motion 缺失
- 動效與操作意圖不一致

請按嚴重度排序，先只輸出問題，不直接修改。
```

## 東尼目前的使用建議

用在工作台：

- Ctrl／⌘K Command Palette
- 側欄收合
- Inspector 切換
- Toast
- 狀態更新
- 小幅 hover

不要使用：

- 大量視差
- 全頁動畫
- 每次換頁都炫技
- 影響長時間工作的動效

---

# 5. AI UI 設計五階段工作流

來源：  
https://hackmd.io/7jP8CQ-zTumZktaqi8aqaw

## 核心觀念

不要等 UI 做壞才補救。  
把不同工作拆開，讓不同 skill／tool 各做自己最擅長的事。

## 實際階段

### 0. 視覺概念探索

用途：

- 完全沒有畫面想法
- 想重設 dashboard
- 想先看 2～3 種方向

輸出：

- concept
- mockup
- 完整 primary screen
- 桌機／手機方向

規則：先看圖，先不要實作。

### 1. 設計決策

用途：

- 固定色彩
- 字體
- 元件語言
- 資訊密度
- UX 原則

輸出：設計方向文件。

### 2. 設計語言建立

用途：

- 把設計方向固定成 `DESIGN.md`
- 讓後續 AI 不會每頁換風格
- 建立可維護的 tokens 與元件規則

### 3. UI 開發

用途：

- 依專案既有 framework 與 component library 落地
- 不重造已有元件
- 不硬編顏色
- 使用 semantic tokens

### 4. UI 開發後評審與精修

用途：

- 找出 AI 味
- 修視覺層級
- 修間距、字重、對齊、按鈕與空狀態
- 必要時 redesign

### 5. 上線前檢查

檢查：

- accessibility
- WCAG
- focus state
- 鍵盤操作
- 螢幕閱讀器
- 色彩對比
- mobile
- loading／error／empty state
- dark mode
- code-level 問題

## 中文操作口訣

```text
沒畫面：先做 concept。
有方向：寫設計決策。
已定稿：做 DESIGN.md。
要開發：依元件系統實作。
做完了：設計 QA＋精修。
要上線：Accessibility＋Responsive＋功能檢查。
```

## 東尼目前的使用建議

「東尼多元宇宙」改版順序：

1. 保存舊版截圖與 Git Tag。
2. 先做 Dashboard／Cases／Projects 三張 concept。
3. 選一個方向。
4. 產出自己的 DESIGN.md。
5. 先修正四個獨立路由。
6. 再換 UI。
7. 完成後才加 Emil motion。
8. 最後做上線前檢查。
9. Access、Owner guard、隱私邊界不能因 UI 改版被破壞。

---

# 總結：每個來源一句話

- `website-clone`：看結構與工具，不拿來定品牌。
- `awesome-design-md`：把別人的設計語言轉成自己的 AI 規格。
- Level UP 流程：先 briefing、再參考圖、最後才寫 code。
- Emil Skill：畫面完成後再做必要動效與動畫 QA。
- 五階段工作流：管理整個 UI 專案的正確順序。
