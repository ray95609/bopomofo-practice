## ADDED Requirements

### Requirement: 貼紙隨機分配
系統必須能隨機選擇一張玩家尚未擁有的貼紙作為獎勵。如果所有貼紙都已收集，則隨機選擇任意一張。

#### Scenario: 獲得新貼紙
- **WHEN** 擊敗魔王後觸發獎勵流程，且玩家仍有未收集的貼紙
- **THEN** 系統必須選取一張未擁有的貼紙 ID 並將其加入收集清單

#### Scenario: 所有貼紙已收集
- **WHEN** 擊敗魔王後觸發獎勵流程，且玩家已擁有全部 10 款貼紙
- **THEN** 系統隨機選取一張已擁有的貼紙，並在顯示時標註為「已收集」

### Requirement: 貼紙持久化儲存
系統必須使用 `localStorage` 儲存玩家的貼紙收集狀態。

#### Scenario: 儲存收集紀錄
- **WHEN** 玩家獲得新貼紙
- **THEN** 系統必須即時更新 `localStorage` 中的 `collectedIds` 陣列

#### Scenario: 載入收集紀錄
- **WHEN** 頁面初始化載入時
- **THEN** 系統必須從 `localStorage` 讀取並還原貼紙收集狀態
