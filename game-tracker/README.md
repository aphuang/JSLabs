# 🎮 AP's Game Progress Tracker

遊戲進度追蹤系統 | 網頁版應用 | 支持在線同步存檔

[![Deploy to Pages](https://github.com/你的用戶名/game-tracker/actions/workflows/pages.yml/badge.svg)](https://github.com/你的用戶名/game-tracker)

**[▶️ 點這裡打開應用](https://你的用戶名.github.io/game-tracker/)** | [📖 完整說明書](#-功能介紹) | [🚀 快速部署](#-快速開始)

---

## 📸 功能預覽

```
🎮 遊戲表         🏁 里程碑表       📅 週計劃表
├─ 9 款遊戲       ├─ 38 個里程碑     ├─ 11 個時段
├─ 實時進度條     ├─ 三種狀態       ├─ 完成度追蹤
└─ 自動計算       └─ 自動更新       └─ 統計面板
```

---

## ✨ 核心特性

✅ **完全本地運行** - 無需後端，純 HTML5 + JavaScript  
✅ **自動保存** - 所有修改立即保存到瀏覽器  
✅ **JSON 導出/導入** - 支持備份和跨設備同步  
✅ **深色/淺色主題** - 完全響應式設計  
✅ **離線使用** - 無需網際網路連線  
✅ **免費託管** - 部署到 Github Pages 完全免費

---

## 🚀 快速開始

### 方式 1：直接打開（最簡單）

```bash
# 1. 下載 game-tracker.html
# 2. 雙擊打開
# 完成！🎉
```

### 方式 2：部署到 Github Pages（推薦）

1. **[建立新倉庫](https://github.com/new)**
   - 名稱：`game-tracker`
   - 勾選「Add README」

2. **上傳文件**
   - 點擊「Add file」→「Upload files」
   - 選擇 `game-tracker.html`

3. **啟用 Pages**
   - Settings → Pages
   - Source：選 `main` 分支
   - 點擊「Save」

4. **完成！**
   ```
   https://你的用戶名.github.io/game-tracker
   ```

詳見 [GITHUB-DEPLOY-QUICK.md](./GITHUB-DEPLOY-QUICK.md)

---

## 📖 功能介紹

### 🎮 遊戲表

| 功能 | 說明 |
|------|------|
| 進度條 | 自動計算：完成里程碑 / 總里程碑 |
| 優先級 | High / Medium / Low |
| 里程碑數 | 該遊戲的總里程碑數 |
| 編輯/刪除 | 修改遊戲名稱或移除遊戲 |

**預設 9 款遊戲：**
1. Kingdom Come: Deliverance 2
2. Grim Dawn
3. Metro Exodus
4. Dead Cells
5. Street Fighter 6
6. Euro Truck Simulator 2
7. Gran Turismo 7
8. 桃太郎電鐵中文版
9. 惡魔靈魂重製版

### 🏁 里程碑表

38 個里程碑，追蹤每個遊戲的進度

**3 種狀態：**
- 🔵 Not Started（未開始）
- 🟡 In Progress（進行中）
- 🟢 Completed（已完成）

**操作方式：**
1. 點擊「狀態」下拉菜單
2. 選擇「Completed」
3. Games 表進度條自動更新 ✨

### 📅 週計劃表

追蹤每週 11 個時間槽的完成情況

| 時段 | 預計遊戲 | 時長 |
|------|---------|------|
| 週一～五晚間 | 各式遊戲 | 2hr × 5 |
| 週六下午 | KCD2/Grim Dawn | 3-4hr |
| 週六晚間 | 桃太郎電鐵 | 2hr |
| 週日下午 | 惡魔靈魂 | 3-4hr |
| 週日晚間 | Metro Exodus | 2hr |

---

## 💾 數據備份 & 同步

### 導出備份

```
1. 點擊「📥 導出」按鈕
2. 瀏覽器下載 JSON 檔案
3. 將 JSON 上傳到 Github
```

### 跨設備恢復

```
1. 從 Github 下載 JSON
2. 打開應用
3. 點擊「📤 匯入」
4. 貼上 JSON 內容
```

### 自動 Git 同步

```bash
# 定期導出並提交
git add *.json
git commit -m "backup: Update game progress"
git push origin main
```

---

## 📱 使用場景

- 📊 **多遊戲進度管理** - 同時追蹤多款遊戲
- ⏰ **時間規劃** - 確保每週遊玩計劃
- 🎯 **里程碑追蹤** - 監控具體進度
- 📈 **統計分析** - 看進度百分比
- 🔄 **跨設備同步** - 手機/電腦無縫切換

---

## 🔧 自定義

### 修改預設遊戲

編輯 `game-tracker.html`，找到 `defaultGames` 部分：

```javascript
const defaultGames = [
    { id: 1, name: '你的遊戲名稱', priority: 'High' },
    // 修改後儲存重新打開即可
];
```

### 修改顏色方案

在 CSS 部分修改主色：
```css
/* 改變 #2563eb 為你喜歡的顏色 */
background: #2563eb;
```

---

## 📊 數據格式

完整的 JSON 結構：

```json
{
  "games": [
    {
      "id": 1,
      "name": "遊戲名稱",
      "priority": "High"
    }
  ],
  "milestones": [
    {
      "id": 1,
      "name": "里程碑名稱",
      "gameId": 1,
      "status": "Completed",
      "expectedWeek": "1-2"
    }
  ],
  "schedule": [
    {
      "id": 1,
      "timeSlot": "週一晚間",
      "games": "遊戲名稱",
      "duration": "2hr",
      "completed": true
    }
  ]
}
```

---

## ❓ 常見問題

**Q: 數據會丟失嗎？**  
A: 不會。數據存儲在瀏覽器 localStorage，只要不清除緩存就不會丟失。建議定期導出備份。

**Q: 可以在多台設備上同步嗎？**  
A: 可以。導出 JSON 到 Github，在另一台設備上導入即可。

**Q: 離線可以用嗎？**  
A: 可以。打開過一次後會被瀏覽器緩存，無需網際網路。

**Q: 如何重置所有數據？**  
A: 點擊「🔄 重置」按鈕恢復默認狀態。

**Q: 支援手機嗎？**  
A: 完全支持。響應式設計適應所有屏幕大小。

---

## 📁 文件說明

| 文件 | 說明 |
|------|------|
| `game-tracker.html` | 主應用（唯一需要的文件） |
| `README-WEBAPP.md` | 完整的應用使用說明 |
| `GITHUB-DEPLOY-QUICK.md` | Github Pages 快速部署指南 |
| `Notion_Import_Guide.md` | Notion 資料庫導入指南 |
| `game_progress_milestones.md` | 38 個里程碑詳細列表 |
| `games_database.csv` | 9 款遊戲資料 |
| `milestones_database.csv` | 里程碑資料 |
| `weekly_schedule.csv` | 週計劃資料 |

---

## 🎯 下一步

- [ ] 下載 `game-tracker.html`
- [ ] 在瀏覽器中測試
- [ ] 部署到 Github Pages（可選）
- [ ] 開始追蹤遊戲進度！

---

## 🚀 部署狀態

- ✅ 本地運行：無需配置
- ✅ Github Pages：完全支持
- ✅ 其他靜態服務器：完全支持
- ✅ 自訂域名：支持（見部署指南）

---

## 📞 支援

遇到問題？

1. 查看 [README-WEBAPP.md](./README-WEBAPP.md) 的常見問題
2. 查看 [GITHUB-DEPLOY-QUICK.md](./GITHUB-DEPLOY-QUICK.md)
3. 提交 Issue 到此倉庫

---

## 📝 許可證

MIT License - 自由使用和修改

---

## 🙏 致謝

感謝使用這個應用！  
如果有幫助，請給個 ⭐ Star！

---

**簡單 • 強大 • 完全免費**

🎮 開始追蹤你的遊戲進度吧！
