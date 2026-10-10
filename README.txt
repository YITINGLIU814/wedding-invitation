# 吳嘉修 & 劉誼婷 wedding invitation

## 檔案內容
- `index.html`：完整長頁式網站，含手機版排版、捲動淡入動畫、婚宴資訊與 Google 地圖連結。
- `images/`：請放入婚紗照，檔名如下：
  - `hero.jpg`：首頁主視覺照片
  - `photo-1.jpg`：戶外婚紗照
  - `photo-2.jpg`：棚拍婚紗照
  - `photo-3.jpg`：其他婚紗照
  - `closing.jpg`：結尾背景照片（可與 hero 使用同一張）
- `index.html` 內 `RSVP_FORM_URL`：完成 Google 表單後，貼上表單的公開填寫網址。

## Google 表單欄位建議
依照此順序新增問題：
1. 姓名（簡答，必填）
2. 聯絡方式（簡答，必填；可填手機或 LINE ID）
3. 與新人的關係（單選，必填：新娘親友／新郎親友／雙方共同親友／其他）
4. 是否出席（單選，必填：會出席／不克出席）
5. 一般座位人數（簡答，數字驗證，必填）
6. 兒童椅數量（簡答，數字驗證，沒有請填 0）
7. 自備娃娃車數量（簡答，數字驗證，沒有請填 0）
8. 素食人數（簡答，數字驗證，沒有請填 0）
9. 是否需要紙本喜帖（單選，必填：需要／不需要）
10. 收件者姓名（簡答）
11. 郵遞區號（簡答）
12. 收件地址（段落）
13. 有什麼話想偷偷對我們說🤍（段落，非必填）

### 依條件顯示紙本喜帖地址欄位
Google 表單可用「依據答案前往不同區段」：
- 第 1 區段：基本資料、出席資訊、是否需要紙本喜帖
- 選「需要」→ 第 2 區段：收件者姓名、郵遞區號、收件地址 → 提交表單
- 選「不需要」→ 直接前往提交
請注意：Google 表單的分區跳轉通常依「單選題」設定。若想讓「不出席」的人跳過人數欄位，可另設區段並規劃跳轉，避免誤填。

## 免費發布到 GitHub Pages
1. 登入/建立 GitHub 帳號。
2. 建立公開 Repository，例如 `wedding-invitation`。
3. 上傳 `index.html` 和 `images` 資料夾。
4. 開啟 Repository → Settings → Pages。
5. 在 Build and deployment 選 `Deploy from a branch`；Branch 選 `main`、資料夾選 `/ (root)`，按 Save。
6. 等待部署完成，網址格式通常為 `https://你的GitHub帳號.github.io/wedding-invitation/`。
7. 用手機開啟網址測試。

## 把表單接到網站
1. 在 Google Forms 建立表單。
2. 按「傳送」或「發布」並複製公開填寫網址（不是編輯網址）。
3. 開啟 `index.html` 編輯，搜尋 `const RSVP_FORM_URL = "";`
4. 把網址放在雙引號內，例如 `const RSVP_FORM_URL = "https://docs.google.com/forms/d/e/1FAIpQLSe14kMaGcgnXiJWjuWXnQooZRbPdztnwaIJXD_WOyyV_3HYrQ/viewform?embedded=true
";`
5. 儲存並重新上傳 `index.html` 到 GitHub，網站就會顯示可用的回覆按鈕。
6. 在 Google 表單的「回覆」頁籤，連結 Google 試算表，方便整理出席人數與地址。

## 上線前確認
- 將婚紗照片縮小到適合網頁使用的大小（建議單張約 500KB–1.5MB，JPG/WebP）。
- 確認日期、地址、導航連結。
- 婚宴流程、交通與停車資訊仍是待填欄位，不會自行編造。
- 試填表單，確認回覆確實進入 Google 試算表。
- 因表單會收集聯絡方式及住址，請只收集婚禮安排需要的資料，並避免公開分享回覆試算表。


## 讓 Google 表單直接顯示在電子喜帖內（內嵌版）
這個版本已改成「表單直接嵌入喜帖頁面」，賓客不必跳出網站。表單仍由 Google Forms 接收回覆，並可連結 Google 試算表統計。

1. 完成 Google 表單所有題目與條件式區段。
2. 在 Google 表單右上方找到「發布／傳送」或分享功能，確保表單已開放填寫。
3. 開啟表單的「嵌入 HTML」功能（通常以 `<>` 圖示表示）。
4. 複製提供的 iframe HTML，找到其中 `src="..."` 的網址，只複製雙引號內的網址。通常網址會包含 `embedded=true`。
5. 開啟 `index.html`，搜尋：
   `const RSVP_EMBED_URL = "";`
6. 把剛剛複製的嵌入網址貼到引號中，例如：
   `const RSVP_EMBED_URL = "https://docs.google.com/forms/d/e/FORM_ID/viewform?embedded=true";`
   請使用你自己的真實網址，不要照抄範例。
7. 儲存 `index.html`，重新上傳至 GitHub Pages。
8. 開啟公開網站，滑到「期待與你相見」區段，確認表單直接出現在喜帖內並試填一次。
9. 在 Google 表單「回覆」頁籤點選綠色試算表圖示，建立回覆試算表。

### 注意
- Google 表單內嵌後的表單外觀主要由 Google 表單的主題設定控制；網站外層的喜帖仍維持韓系簡約風格。
- 內嵌表單高度目前設為 1550px。若你的表單較長，可在 `index.html` 搜尋 `height="1550"`，調整為 1800 或 2100。
- 需要先將 Google 表單發布並確認有填寫權限，否則網站訪客可能無法填寫。
- 若使用條件式區段，請在預覽中測試「需要紙本喜帖」與「不需要」兩條路徑。
