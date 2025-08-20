# 🚀 飛牛 NAS 媒體服務器一鍵部署腳本

歡迎來到我的 GitHub 倉庫！這個腳本是我為飛牛 NAS 使用者設計的，旨在簡化媒體服務器套件的部署流程，讓所有人都能輕鬆建立自己的影音中心。

這個腳本由 Eric 創建，如果你覺得它有幫助，歡迎訂閱我的 YouTube 頻道：
**[📺 Eric's YouTube Channel](https://www.youtube.com/@Eric-f2v)**

---

## ✨ 腳本功能

本腳本將自動完成以下所有步驟：

* **自動化目錄創建**：在 `/vol1/1000` 下建立完整的目錄結構，包括 `docker`、`media`、`movie`、`tv` 和 `downloads`。
* **交互式設定**：在執行時會提示你輸入 PUID 和 PGID，如果你不確定，直接按 Enter 即可使用默認值 `1000`。
* **一鍵部署**：為每個應用程式自動生成 Docker Compose 檔案並啟動容器。
* **包含多個應用**：
    * **Jellyfin** (使用 `nyanmisaka/jellyfin` 映像檔) - 媒體服務器
    * **Jellyseerr** - 媒體請求和管理
    * **Jackett** - 索引器管理
    * **qBittorrent** - 下載工具
    * **Sonarr** - 電視劇自動化管理
    * **Radarr** - 電影自動化管理
    * **Bazarr** - 字幕自動化下載

---

## 💡 如何使用

1.  **下載腳本**：
    * 將 `deploy_media_stack.sh` 腳本檔案下載到你的電腦。
    * 使用 SSH、SFTP 或其他方式將腳本上傳到你的 NAS，建議放在 `/vol1/1000` 目錄下。

2.  **給予執行權限**：
    * 透過 SSH 連線到你的 NAS 終端機。
    * 導航到腳本所在的目錄，並執行以下命令：
        ```bash
        chmod +x deploy_media_stack.sh
        ```

3.  **執行腳本**：
    * 以 `sudo` 權限執行腳本：
        ```bash
        sudo ./deploy_media_stack.sh
        ```
    * 腳本會引導你輸入 PUID 和 PGID，然後自動完成部署。

---

## 🌐 服務訪問地址

腳本執行成功後，你可以透過你的 NAS IP 和對應埠號來訪問每個服務的網頁介面：

* **Jellyfin**: `http://<NAS_IP>:8096`
* **Jellyseerr**: `http://<NAS_IP>:5055`
* **Jackett**: `http://<NAS_IP>:9117`
* **qBittorrent**: `http://<NAS_IP>:8080`
* **Sonarr**: `http://<NAS_IP>:8989`
* **Radarr**: `http://<NAS_IP>:7878`
* **Bazarr**: `http://<NAS_IP>:6767`