# 🚀 快速部署到 Github Pages（5 分鐘）

## 前提條件

✅ 已安裝 Git  
✅ 有 Github 帳號  
✅ 已下載 `game-tracker.html`

---

## 3 個步驟完成部署

### 步驟 1️⃣：建立 Github 倉庫

1. 登入 [Github](https://github.com)
2. 點擊右上角「+」→ 「New repository」
3. 輸入倉庫名稱，例如：`game-tracker`
4. 選擇「Public」（必須，這樣才能用 Pages）
5. 勾選「Add a README file」
6. 點擊「Create repository」

---

### 步驟 2️⃣：上傳文件

**方式 A：Web 上傳（最簡單）**

1. 在新倉庫頁面，點擊「Add file」→「Upload files」
2. 將 `game-tracker.html` 拖到上傳區
3. 修改提交信息：`Add game tracker application`
4. 點擊「Commit changes」

**方式 B：Git 命令上傳（如果懂 Git）**

```bash
git clone https://github.com/你的用戶名/game-tracker.git
cd game-tracker

# 複製 game-tracker.html 到此資料夾

git add game-tracker.html
git commit -m "Add game tracker application"
git push origin main
```

---

### 步驟 3️⃣：啟用 Pages

1. 進入倉庫 → 點擊「Settings」
2. 左側邊欄點擊「Pages」
3. 在「Source」選擇 `main` 分支
4. 在「/root」（根目錄）旁邊點擊「Save」
5. 頁面會重新加載，看到如下信息：

```
Your site is live at:
https://你的用戶名.github.io/game-tracker
```

🎉 **完成！你的應用已上線！**

---

## 📱 訪問你的應用

打開瀏覽器，進入：
```
https://你的用戶名.github.io/game-tracker
```

就能看到你的遊戲進度追蹤系統！

---

## 📤 日常使用流程

### 備份進度到 Git

1. 在應用中點擊「📥 導出」
2. 瀏覽器會下載 JSON 檔案
3. 將該檔案上傳到 Github 倉庫：

```bash
# 在倉庫資料夾中
mv 下載的.json檔案 progress-backup.json
git add progress-backup.json
git commit -m "Backup game progress"
git push origin main
```

### 在另一台電腦上恢復

1. 從 Github 下載 JSON 檔案
2. 打開你的應用：https://你的用戶名.github.io/game-tracker
3. 點擊「📤 匯入」
4. 貼上 JSON 內容並確認

---

## 🔗 有用的鏈接

| 功能 | 鏈接 |
|------|------|
| 你的應用 | `https://你的用戶名.github.io/game-tracker` |
| 倉庫設置 | `https://github.com/你的用戶名/game-tracker/settings` |
| Pages 設置 | `https://github.com/你的用戶名/game-tracker/settings/pages` |

---

## ❓ 常見問題

**Q: 我上傳了文件但 Pages 還沒出現？**
A: Github Pages 通常需要 2-5 分鐘才能部署。重新整理頁面試試。

**Q: 文件叫什麼名字？**
A: 建議命名為 `game-tracker.html` 或 `index.html`（Github Pages 優先載入 index.html）

**Q: 能更改 URL 嗎？**
A: 
- 倉庫名稱 = URL 路徑，改倉庫名稱即改 URL
- 用戶名無法改變（改用戶名會改 https://新用戶名.github.io）

**Q: 我可以在手機上用嗎？**
A: 可以！用手機瀏覽器打開同一 URL 即可。

---

## 🎯 完成後的效果

✅ 應用部署在 `https://你的用戶名.github.io/game-tracker`  
✅ 任何設備通過網址即可訪問  
✅ 數據自動保存到瀏覽器  
✅ 支持 JSON 導出備份到 Git  
✅ 支持在另一台設備上匯入恢復

---

## 💡 進階：自訂義域名（可選）

如果你有自己的域名，可以設置：

1. Settings → Pages
2. 在「Custom domain」輸入你的域名，例如：`games.yourdomain.com`
3. 在你的域名 DNS 設置中加入 Github 提供的記錄
4. 等待 DNS 生效（可能需要 24 小時）

---

## 🆘 需要幫助？

1. 檢查 [Github Pages 文檔](https://docs.github.com/en/pages)
2. 查看 [Github Community](https://github.community)
3. 提交 Issue 到倉庫

---

**現在就開始部署吧！** 🚀
