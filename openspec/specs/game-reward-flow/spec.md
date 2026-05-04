# game-reward-flow Specification

## Purpose
TBD - created by archiving change add-sticker-reward-system. Update Purpose after archive.
## Requirements
### Requirement: 魔王擊敗獎勵轉向
系統必須將擊敗魔王（第 6 關）後的獎勵從單純的糖果 Emoji 改為觸發貼紙抽獎系統。

#### Scenario: 擊敗魔王
- **WHEN** `defeatedMonsters` 變為 6 時
- **THEN** 系統必須顯示「獲得貼紙」彈窗而非原本的糖果彈窗

#### Scenario: 關卡重置與狀態更新
- **WHEN** 完成貼紙領取流程並重新開始遊戲
- **THEN** 系統必須正確重置怪物進度，並保留 `localStorage` 中的貼紙收集狀態

