## 1. 基礎架構與儲存邏輯 (Sticker Engine)

- [x] 1.1 在 JavaScript 中定義 `STICKERS_CONFIG` 物件，包含 10 款貼紙的 ID、名稱與 SVG 路徑。
- [x] 1.2 實作 `StickerManager` 類別，負責讀取/寫入 `localStorage` (鍵名：`baby_typing_stickers`)。
- [x] 1.3 實作隨機抽選貼紙的函式，優先挑選未獲得的 ID。

## 2. 收集冊介面實作 (Sticker Book UI)

- [x] 2.1 在 `index.html` 的 `game-status-bar` 底部新增「收集冊」按鈕。
- [x] 2.2 實作收集冊 Modal 的 HTML 結構與基礎 CSS 樣式（網格佈局）。
- [x] 2.3 實作貼紙渲染邏輯：已獲得顯示彩色，未獲得顯示灰階與問號背景。
- [x] 2.4 新增開啟/關閉收集冊的 JavaScript 函式。

## 3. 獎勵流程整合 (Reward Flow)

- [x] 3.1 修改 `finishWord` 函式，當 `defeatedMonsters === 6` 時改為呼叫 `showStickerReward()`。
- [x] 3.2 實作 `showStickerReward()` 彈窗，展示獲得的貼紙與文字提示。
- [x] 3.3 實作「飛入收集冊」動畫：從彈窗中央縮放並移動至左下角按鈕位置。

## 4. 貼紙視覺設計 (Sticker Assets)

- [x] 4.1 實作奧特曼與皮卡丘的 SVG/CSS 資源。
- [x] 4.2 實作胖丁與米奇的 SVG/CSS 資源。
- [x] 4.3 實作維尼、馬力歐與奇諾比奧的 SVG/CSS 資源。
- [x] 4.4 實作太空貓、注音精靈與傳說金龍的 SVG/CSS 資源。

## 5. 測試與優化 (Polish)

- [x] 5.1 測試移動端觸控體驗，確保按鈕與 Modal 操作順暢。
- [x] 5.2 檢查 `localStorage` 跨頁面重新整理的持久性。
- [x] 5.3 優化獲獎音效與視覺特效（紙屑噴發）。
