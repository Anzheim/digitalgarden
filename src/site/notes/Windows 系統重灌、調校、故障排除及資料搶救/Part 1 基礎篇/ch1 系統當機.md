---
{"dg-publish":true,"permalink":"/Windows 系統重灌、調校、故障排除及資料搶救/Part 1 基礎篇/ch1 系統當機/"}
---

# 1. 當機原因與預防措施
## 當機原因
### 1. 硬碟分割表
硬碟分割表儲存系統指令，當硬碟分割表指令被修改或損毀，將導致無法載入作業系統。(多半是硬碟問題)
### 2. 系統選單
系統選單出錯，導致無法讀取系統檔案、無法進入下一階段的系統啟動進程，所以無法進入系統。
### 3. 遺失關鍵檔案
系統啟動時會檢查是否移師關鍵檔案，若有遺失或毀損就會卡在此階段，無法進入系統。
### 4. 登錄檔毀損
登錄檔紀錄系統和應用程式的重要訊息，若毀損可能導致成是無法載入，系統也會停留在某一階段。
### 5. 病毒入侵
病毒感染檔案或程式後，可能破壞系統檔案、改變硬碟訊息，導致系統容易被破壞。
### 6. 硬碟故障
硬碟出現物理性或邏輯性的損毀，且損毀區域恰與系統啟動相關。
### 7. 軟/硬體衝突
即使進入了 OS，可能因無法調用的軟/硬體資源而卡住。這也是常見狀況。

---
## 系統當機影響的資料
### 應用程式
大多數應用程式需在登入檔中加入訊息，重灌會導致登錄檔恢復到原始狀態，應用程式便須重新安裝。
### 使用者資料
與帳戶相關的設定或媒體櫃的資料會遺失，但像 Win 10 會將帳戶設定存在雲端，只要用相同帳戶登入就不會有設定上的損失，所以具體損失也是看系統版本。
### 系統碟上的檔案
如果不重新格式化硬碟就重灌，Windows 目錄外的其他檔案(桌面、圖片、下載、文件)就不會有什麼影響，但系統所在的 Windows 目錄和目錄下的檔案必被清除，原先儲存的系統更新和還原點等都不會存在了。
仍建議先備份，安裝過程不小心格式化硬碟就全部再見，就算個人檔案還在，依賴的登錄檔和系統設定已重置，已安裝的軟體可能無法正常運行。若用「重設此電腦」重灌 Windows，某些選項可能刪掉個人檔案。
## 降低當機風險
### 即時更新
提高系統穩定性並修正系統缺陷。
### 安裝防毒並定時掃描
不要太相信防毒的監控能力，主動掃描更安全。
### 謹慎使用網路和軟體
不瀏覽不安全網站、下載安裝防毒也要透過正規管道。
### 定期整理硬碟和安裝的程式
傳統物理硬碟 HDD 刪除檔案的過程會產生不連續的儲存空間與區域，降低硬碟使用效率而影響系統讀寫速度。定期整理有助於保持系統效能，盡量移除不再使用的應用程式，可減少浪費磁碟空間和登錄檔體積，有益於保持系統效能。
# 2. 當機修復方法
## 1. 重設或重新整理電腦
近似重灌，適用不熟悉安裝 OS 的使用者。
## 2. 升級後不穩定，回到舊系統
只有升級後的一段時間內可以使用回復功能。
## 3. 修復硬碟集資料搶救
Win 10 內建修復邏輯壞軌的工具。參考 ch3, ch4。
## 4. 電腦散熱
CPU 散熱不佳導致的硬體故障就不是用重灌能解的。
# 3. 重灌步驟
## 1. 備份必要資料
參考 ch4, ch5。
## 2. 安裝前準備工作
參考 ch7, ch8。
## 3. 安裝乾淨的系統
在系統純淨時做好還原點（安裝基本功能、防毒、應用程式並調整好網路環境後建立還原點），參考 ch6。
## 4. 提升安全性
e.g. Windows 防火牆. 參考 ch9。
# 4. 提升系統效能
參考 ch8~ch10 軟硬體提升系統效能的方法，
## 最佳化啟動設定
參考 ch8。
### 1. 最佳化啟動系統時間：節省開機時間
### 2. 最佳化 BIOS：電腦硬體元件運作穩定、增加執行效能

### 3. 減少開機載入的服務：降低系統資源占用的情況

## 強化資料安全和系統速度
參考 ch9 最佳化系統設定，增強一般資料安全性、系統必要加密、正確管理硬碟、電源計畫、最佳 I/O 裝置，提升系統易用性。
## 最佳化網路設定
參考 ch10。
# 5. 多重系統的合理安裝順序
安裝多個系統不一定要安裝在另一個磁碟區上，可用 VHD 或虛擬機器。參考 ch12 安裝方案。
## 進階安裝
### 虛擬機器
多重系統：將不同 OS 安裝在電腦的不同磁碟中，一次只能登入一個系統，要登入另一系統需登出並重新啟動電腦。
虛擬機器：利用虛擬機建立作業系統，可同時使用兩個系統，解決系統與應用軟體不相容的問題。
### VHD
VHD 虛擬磁碟從 Win 7 開始，可打造不怕毀損的系統，利用 VPC 格式的虛擬磁碟 (VHD 檔案) 開機，可直接存取硬體資源(CPU, RAM, hard disk 及一般虛擬化無法模擬的顯卡)，而提升虛擬磁碟的效能。參考 ch12 建立 VHD 開機的方法。
### UEFI
Win 10 安裝前部署，讓開機速度變快，即使沒有 SSD 也可以快速開機。
# 6. 系統升級注意
升級系統不一定提升效能，若系統版本差異太大，重灌時可能無法保存系統資料。