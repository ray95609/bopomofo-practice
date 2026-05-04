# sticker-assets Specification

## Purpose
TBD - created by archiving change add-sticker-reward-system. Update Purpose after archive.
## Requirements
### Requirement: 貼紙視覺設計
系統必須預定義 10 款不使用 Emoji 的可愛童趣風貼紙資源。

#### Scenario: 貼紙渲染
- **WHEN** 系統需要顯示編號為 1 的貼紙（奧特曼）
- **THEN** 系統必須正確渲染預定義的 SVG 內容或 CSS 樣式組合

### Requirement: 貼紙飛行特效
當獲得新貼紙時，系統必須播放從螢幕中央飛向收集冊按鈕的動畫。

#### Scenario: 觸發獎勵動畫
- **WHEN** 玩家點擊獲得新貼紙彈窗的按鈕
- **THEN** 系統必須建立一個貼紙副本，並執行縮小且移動至收集冊按鈕座標的過渡動畫

