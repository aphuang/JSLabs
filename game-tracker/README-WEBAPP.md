# 🎮 AP's 遊戲進度追蹤系統 - 網頁版

完整的在線遊戲進度管理工具，支持實時同步存檔。

## 📋 功能特性

✅ **三個主要模块**
- 🎮 **遊戲表** - 管理 9 款遊戲，實時顯示進度條
- 🏁 **里程碑表** - 追蹤 38 個里程碑，一鍵標記完成
- 📅 **週計劃表** - 追蹤 11 個時間槽，監控週完成度

✅ **核心功能**
- 🌐 完全在瀏覽器運行，無需後端服務
- 💾 自動保存到本地存儲（localStorage）
- 🔄 支持 JSON 導出/導入備份
- 🎨 深色/淺色模式切換
- 📊 實時統計數據展示
- 📱 完全響應式設計

✅ **數據同步**
- 所有修改立即自動保存
- 可隨時導出 JSON 備份到 Git
- 支持多設備導入同步

---

## 🚀 快速開始

### 方式 1：直接打開 HTML 文件

1. 下載 `game-tracker.html`
2. 在瀏覽器中打開該文件
3. 開始使用！數據會自動保存

### 方式 2：部署到 Github Pages（推薦）

#### 第一步：建立 Github 倉庫

```bash
# 1. 在 Github 創建新倉庫
# 名稱建議：game-tracker 或 gaming-hub
# 勾選「Add a README file」

# 2. Clone 到本地
git clone https://github.com/你的用戶名/game-tracker.git
cd game-tracker
```

#### 第二步：添加文件

```bash
# 將 game-tracker.html 複製到倉庫根目錄
cp game-tracker.html .

# 可選：創建 index.html 重定向（Github Pages 會自動找 index.html）
# 或直接將 game-tracker.html 重命名為 index.html
mv game-tracker.html index.html
```

#### 第三步：推送到 Github

```bash
git add .
git commit -m "feat: Add game tracking system"
git push origin main
```

#### 第四步：啟用 Github Pages

1. 進入倉庫設置（Settings）
2. 左側邊欄找到「Pages」
3. 在「Source」選擇 `main` 分支
4. 選擇根目錄（/）
5. 點擊「Save」

幾分鐘後，你的應用會部署到：
```
https://你的用戶名.github.io/game-tracker
```

或如果命名為 `index.html`，甚至可以：
```
https://你的用戶名.github.io/game-tracker/
```

---

## 📖 使用指南

### 🎮 遊戲表

| 功能 | 說明 |
|------|------|
| 進度條 | 自動計算：該遊戲已完成的里程碑 / 總里程碑數 |
| 里程碑數 | 該遊戲的里程碑總數 |
| 編輯 | 修改遊戲名稱 |
| 刪除 | 刪除遊戲及其所有里程碑 |

**統計面板：**
- 總遊戲數
- 已完成遊戲數（所有里程碑都標記為完成）
- 平均進度百分比

### 🏁 里程碑表

**3 種狀態：**
- 未開始 → 進行中 → 已完成

**常用操作：**
1. 點擊「狀態」下拉菜單直接改為「已完成」
2. Games 表的進度條會自動更新
3. 預期週數用於規劃參考

**統計面板：**
- 總里程碑數
- 已完成數
- 進行中數

### 📅 週計劃表

**完成時間槽：**
1. 點擊「完成」欄的複選框 ✓
2. 系統自動計算本週完成度

**統計面板：**
- 本週時間槽數
- 已完成槽數
- 完成百分比

---

## 💾 數據導出 & 備份

### 導出數據

1. 點擊頁面上方「📥 導出」按鈕
2. 瀏覽器會下載 JSON 檔案（如 `game-tracker-2026-09-07.json`）
3. 保存該檔案到 Git 倉庫

### 定期備份到 Git

```bash
# 使用腳本自動導出並提交

#!/bin/bash
# 在頁面導出 JSON，然後執行：

git add *.json
git commit -m "backup: Update game progress data"
git push origin main
```

### 在另一台設備上恢復

1. 打開應用
2. 點擊「📤 匯入」按鈕
3. 貼上之前導出的 JSON 內容
4. 點擊「確認匯入」

---

## 🔄 跨設備同步

### 方案 A：手動 Git 同步（推薦）

1. **設備 A 上：**
   - 使用應用並修改數據
   - 點擊「📥 導出」
   - 將 JSON 上傳到 Git

2. **設備 B 上：**
   - 從 Git 下載最新 JSON
   - 打開應用
   - 點擊「📤 匯入」並貼上 JSON

### 方案 B：雲端儲存

1. 將導出的 JSON 保存到 Google Drive/OneDrive
2. 在其他設備上下載並匯入

### 方案 C：自動同步腳本

可以使用 GitHub Actions 自動同步（進階功能）

---

## 🎨 自定義

### 修改遊戲列表

編輯 `game-tracker.html`，找到 `defaultGames` 部分：

```javascript
const defaultGames = [
    { id: 1, name: '你的遊戲名稱', priority: 'High' },
    // ... 更多遊戲
];
```

### 修改默認里程碑

編輯 `defaultMilestones` 部分：

```javascript
const defaultMilestones = [
    { id: 1, name: '里程碑名稱', gameId: 1, status: 'Not Started', expectedWeek: '1-2' },
    // ...
];
```

### 修改顏色方案

在 CSS 部分修改 `#2563eb` 為你喜歡的顏色。

---

## 🔍 常見問題

**Q: 我在另一台設備上看不到數據？**
A: 因為 localStorage 是設備本地存儲。需要導出 JSON 並在另一台設備上匯入。

**Q: 數據會丟失嗎？**
A: 不會。數據存儲在你的瀏覽器中。只要不清除 Cookie 和緩存就不會丟失。建議定期導出備份。

**Q: 可以在多個標籤頁同步嗎？**
A: 可以。localStorage 在同一瀏覽器的多個標籤頁中是同步的。

**Q: 如何重置所有數據？**
A: 點擊「🔄 重置」按鈕會恢復到默認狀態。

**Q: Github Pages 支持嗎？**
A: 完全支持！這是完全靜態的 HTML 應用，可以完美部署到 Github Pages。

---

## 📊 數據格式

### JSON 結構

```json
{
  "games": [
    {
      "id": 1,
      "name": "Kingdom Come: Deliverance 2",
      "priority": "High"
    }
  ],
  "milestones": [
    {
      "id": 1,
      "name": "序章完成",
      "gameId": 1,
      "status": "Completed",
      "expectedWeek": "1-2"
    }
  ],
  "schedule": [
    {
      "id": 1,
      "timeSlot": "週一晚間",
      "games": "ETS2 + SF6",
      "duration": "2hr",
      "completed": true
    }
  ]
}
```

---

## 🛠️ 故障排除

### 應用無法打開
- 確保瀏覽器支持 JavaScript
- 嘗試禁用瀏覽器插件（如 AdBlock）
- 使用最新版本的瀏覽器

### 數據無法保存
- 檢查瀏覽器是否允許 localStorage
- 確認沒有在無痕模式打開（無痕模式不會保存數據）
- 清除瀏覽器緩存重試

### 匯入失敗
- 確保 JSON 格式正確
- 複製完整的 JSON 內容（不要有額外空格）
- 檢查 JSON 中是否有中文編碼問題

---

## 📝 許可證

MIT License - 可自由使用和修改

---

## 💡 未來功能（開發中）

- [ ] 雲端自動同步（使用 Supabase/Firebase）
- [ ] 行動應用版本
- [ ] 統計圖表和分析
- [ ] 遊戲打分系統
- [ ] 進度時間軸
- [ ] 多用戶協作

---

## 🎯 快速命令參考

```bash
# 克隆倉庫
git clone https://github.com/你的名字/game-tracker.git

# 推送更新
git add .
git commit -m "Update game progress"
git push origin main

# 查看提交歷史
git log --oneline
```

---

**祝遊戲進度追蹤愉快！** 🎮🎉
