# kaomux

kaomux 是 Windows 上的 SSH 工作台，操作方式仿 MobaXterm：Session 管理、多分頁互動終端、SFTP、主機監控列、MultiExec，以及 SQL（MySQL／MariaDB、PostgreSQL、SQL Server、SQLite）與 Redis 分頁，全在一個視窗裡。介面可切換 English、正體中文、日本語。

這個 repo 只放發布的程式（[Releases](https://github.com/ChadPeng/kaomux-releases/releases)），不含原始碼。

## 下載與執行

1. 到 [最新版 Release](https://github.com/ChadPeng/kaomux-releases/releases/latest) 下載 `kaomux.exe`。
2. 放到自己可以寫入的資料夾，例如桌面或 `文件\kaomux`（不要放 `C:\Program Files`，否則無法自動更新），雙擊執行，不必安裝。
3. 程式沒有程式碼簽章，第一次執行時 Windows 可能顯示「Windows 已保護您的電腦」：按「其他資訊」→「仍要執行」。

想確認檔案沒有損壞，可以比對同一個 Release 裡的 `kaomux.exe.sha256`：

```powershell
(Get-FileHash .\kaomux.exe -Algorithm SHA256).Hash
```

## 更新

- kaomux 開啟後與之後每 6 小時檢查一次新版，預設會在背景下載並驗證 SHA-256，右上角出現「Restart to update to v…」，按下即換成新版（有開著的分頁會先詢問）。
- 不想自動下載：⚙ → General → UPDATES 關掉自動更新，有新版時右上角會出現「Update to v…」，按下才下載。
- 更新後第一次開啟會顯示這幾版的更新說明（What's new）。

## 資料與安全

- 設定與 Session 存在 `%APPDATA%\kaomux`，換新版不會影響。
- 密碼只在你選擇保存時存進密碼保管庫（以目前 Windows 帳號加密），顯示前要先確認身分；SSH 私鑰不保存。
- 第一次連線時要你確認主機金鑰指紋；主機金鑰變更一律拒絕連線。

## 系統需求

- 64 位元 Windows（在 Windows 11 上驗證）。
- 目前只發布 Windows 版；macOS 版尚未發布。
