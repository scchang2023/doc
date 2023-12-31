# GCP (Google Cloud Platform)
[Google Cloud Console](https://console.cloud.google.com/)

### 開始新專案與管理
```
- 新建專案(project id)
- IAM與管理->管理資源可看目前資源使用狀況
- 啟動 compute Engine API
- Compute Engine -> VM 執行個體 ->建立執行個體
- 點選執行個體的SSH連線，可以透過瀏覽器進行SSH連線
```
### 安裝 git
[開始-Git-安裝教學](https://git-scm.com/book/zh-tw/v2/%E9%96%8B%E5%A7%8B-Git-%E5%AE%89%E8%A3%9D%E6%95%99%E5%AD%B8)
```
sudo apt-get install git
```
### 下載專案 crawler_water_meter
```
git clone https://github.com/scchang2023/crawler_water_meter.git

# 更新軟體包列表
sudo apt update
# 安裝 pip, 為 Python 3 安裝 pip 和依賴項
sudo apt install python3-pip
```

### 安裝 crawler_water_meter 會用到的套件
```
pip install selenium
sudo apt update
sudo apt install chromium
```

### 下載安裝 unzip
```
sudo apt install zip
```
### 使用 crontab 設定排程
[參考](https://blog.gtwang.org/linux/linux-crontab-cron-job-tutorial-and-examples/)
### 基本指令

```
# 查看自己的 crontab
crontab -l
# 編輯 crontab 內容
crontab -e
# 刪除 crontab 內容
crontab -r
```
### crontab 設定說明
```
# ┌───────────── 分鐘   (0 - 59)
# │ ┌─────────── 小時   (0 - 23)
# │ │ ┌───────── 日     (1 - 31)
# │ │ │ ┌─────── 月     (1 - 12)
# │ │ │ │ ┌───── 星期幾 (0 - 7，0 是週日，6 是週六，7 也是週日)
# │ │ │ │ │
# * * * * * /path/to/command
```
### crontab 設定範例
```
# 每天早上 8 點 30 分執行
30 08 * * * /home/gtwang/script.sh --your --parameter
# 每週日下午 6 點 30 分執行
30 18 * * 0 /home/gtwang/script.sh --your --parameter
# 每週日下午 6 點 30 分執行
30 18 * * Sun /home/gtwang/script.sh --your --parameter
# 每年 6 月 10 日早上 8 點 30 分執行
30 08 10 06 * /home/gtwang/script.sh --your --parameter
# 每月 1 日、15 日、29 日晚上 9 點 30 分各執行一次
30 21 1,15,29 * * /home/gtwang/script.sh --your --parameter
# 每隔 10 分鐘執行一次
*/10 * * * * /home/gtwang/script.sh --your --parameter
# 從早上 9 點到下午 6 點，凡遇到整點就執行
00 09-18 * * * /home/gtwang/script.sh --your --parameter
```