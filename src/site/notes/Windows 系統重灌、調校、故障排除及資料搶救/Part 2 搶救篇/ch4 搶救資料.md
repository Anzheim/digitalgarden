---
{"dg-publish":true,"permalink":"/Windows 系統重灌、調校、故障排除及資料搶救/Part 2 搶救篇/ch4 搶救資料/"}
---

資料儲存的基本原理：寫入之前也許還有救。
# 資料搶救原理
## 讀取資料
OS 從磁碟區目錄讀取檔案資訊，系統會從檔案的第一個叢集標號開始讀取，遇到 `FF` 結束標號表示檔案結束。
## 寫入資料
OS 找到目錄區閒置的磁區，寫入檔名、大小、時間，在資料儲存區找到閒置空間儲存檔案，並將第一個叢集的叢集號寫入目錄區，全部儲存完後設定一個 `FF` 結束標記。
## 移除資料
移除並沒有完全清除檔案，而是將目錄區檔案第一個字元改成 `E5` 作為移除標記，檔案實體實際上仍存在硬碟中，直到新檔案寫入該位置才會將原檔案覆蓋掉。

資料遺失可能不是被覆蓋，而是檔案分配表資料被變更，讓 OS 認為磁區為空而可寫入其他資料，但其實寫入之前也許還有救。
# 修補檔案
## 檔案無法開啟時
### 複製備份
### 複製到其他PC開啟看看
### 根據檔案類型使用專業修復工具

為避免緩衝中的資料斷電遺失，最好不要重啟電腦，先盡可能修復提升復原機率。
## 修復 mail
用 scanpst.exe
https://support.microsoft.com/zh-tw/office/%E4%BF%AE%E5%BE%A9-outlook-%E8%B3%87%E6%96%99%E6%AA%94-pst-%E8%88%87-ost-25663bc3-11ec-4412-86c4-60458afc5253
## 修復 Office
略
## 修復影片
Digital Video Repair
https://www.risingresearch.com/en/dvr/
## 修復 rar, zip
winRAR
https://rar.tw/
# 誤刪資料
## 找回隨身碟或硬碟被刪的檔案
Recuva
支援 FAT, NTFS, exFat
https://www.ccleaner.com/zh-cn/recuva?srsltid=AfmBOoqzCfxwEr9qIcBT2qnS8BBqLcLYg1wivcm8LjNEvwDeaemEtyl2
## 找回已格式化硬碟的檔案
高階格式化可以恢復，低階無法
DiskGenius [工具] -> [已刪除或格式化後的檔案恢復]
https://www.diskgenius.cn/download.php

