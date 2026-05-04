# sticker-book-ui Specification

## Purpose
TBD - created by archiving change add-sticker-reward-system. Update Purpose after archive.
## Requirements
### Requirement: 收集冊按鈕
系統必須在主畫面的遊戲狀態欄（game-status-bar）中提供一個進入收集冊的入口。

#### Scenario: 點擊收集冊按鈕
- **WHEN** 玩家點擊狀態欄下方的「收集冊」按鈕
- **THEN** 系統必須彈出全螢幕的貼紙收集冊介面

### Requirement: 貼紙牆顯示
收集冊必須以網格形式展示所有 10 款貼紙的狀態。

#### Scenario: 展示未獲得貼紙
- **WHEN** 玩家打開收集冊，且某張貼紙尚未收集
- **THEN** 系統必須以灰階（Grayscale）或剪影形式顯示該貼紙，且不可點擊

#### Scenario: 展示已獲得貼紙
- **WHEN** 玩家打開收集冊，且某張貼紙已經收集
- **THEN** 系統必須顯示該貼紙的彩色原貌，並在點擊時顯示放大視圖或播放相關音效

