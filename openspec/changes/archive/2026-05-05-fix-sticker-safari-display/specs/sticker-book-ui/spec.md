## MODIFIED Requirements

### Requirement: 貼紙牆顯示
系統必須 (SHALL) 以網格形式展示所有 10 款貼紙的狀態，並確保在不同瀏覽器（包括 Safari）及舊版行動裝置上均能正確渲染。

#### Scenario: 展示未獲得貼紙
- **WHEN** 玩家打開收集冊，且某張貼紙尚未收集
- **THEN** 系統必須 (SHALL) 以灰階（Grayscale）或剪影形式顯示該貼紙，且不可點擊

#### Scenario: 展示已獲得貼紙
- **WHEN** 玩家打開收集冊，且某張貼紙已經收集
- **THEN** 系統必須 (SHALL) 顯示該貼紙的彩色原貌，確保圖標在 Safari 瀏覽器中不縮小為零，並在點擊時播放相關音效

## ADDED Requirements

### Requirement: 介面佈局相容性
系統必須 (SHALL) 支援較舊版本的行動裝置瀏覽器，確保網格容器在不支援新 CSS 屬性（如 aspect-ratio）的情況下仍能正常顯示。

#### Scenario: 在舊版 iPad 上開啟收集冊
- **WHEN** 在 iOS 15 以下的 iPad 上開啟收集冊
- **THEN** 系統必須 (SHALL) 確保貼紙網格的每一格保持正確的高度，不可塌陷為零
