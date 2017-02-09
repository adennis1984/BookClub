# Part 2: Execute, Execute, Execute

# CH5. Measure What You Want to Improve - 量測你想改進的東西

## 摘要

### Introduction

* Google 對使用者幸福的最佳指示是 - 長時間點擊 (long click)
> 1. 當有人點擊搜索結果並且不返回搜索頁面，或停留在結果頁面上很長時間。 
> 2. 長時間點擊意味著 Google 已成功顯示用戶一直在搜索的結果。 

* 另一方面，當有人按照鏈接僅立即返回到結果頁面以嘗試另一個鏈接時，則會發生 - 短暫點擊 (short click)
> 1. 表示使用者對結果不滿意。
> 2. 不滿意的用戶也傾向於更改他們的查詢或轉到搜索結果的下一頁。

### Use Metrics to Drive Progress - 使用指標推動進度

“If you can’t measure it, you can’t improve it.” - Peter Drucker, The Effective Executive

* 好的監測指標有下列三種好處：

> * They help you focus on the right things 他們幫助你專注於正確的事情 
> * When visualized over time, good metrics help guard against future regressions 當隨著時間的推移，良好的指標進行視覺化將有助於防止未來可能出現的問題
> * Good metrics can drive forward progress 良好的指標可以推動進步
> * A good metric lets you measure your effectiveness over time and compare the leverage of what you’re doing against other activities you could be doing instead 隨著時間的推移，一個好的指標可以讓你衡量你方法的有效性並比較你目前的行為與其他可將之取代的活動間的槓桿影響力

### Pick the Right Metric to Incentivize the Behavior You Want - 選擇正確的指標來激勵你想要的行為

* Hours worked per week vs. productivity per week 每週工作時間 vs. 每週生產力
* Click-through rates vs. long click-through rates 點擊率 vs. 長期點擊率
* Average response times vs. 95th or 99th percentile response times 平均響應時間 vs. 第95或第99百分位數響應時間
* Bugs fixed vs. bugs outstanding Bugs 修復量 vs. bugs 修復質量
* Registered users vs. weekly growth rate of registered users 註冊用戶 vs. 註冊用戶的每週增長率
* Weekly active users vs. weekly active rate by age of cohort 每週活躍用戶數 vs. 依註冊時間長短分類的每週user活躍率

* The metric you choose influences your decisions and behavior. 你選擇的指標會影響你的決定和行為
* What you don’t measure is important as well. 你不測量什麼也很重要

* 產品和目標越複雜，測量和不測量的選項越多，並且指導工作花費的時間和產生的輸出的靈活性越大。
* 當決定使用哪些指標時，以下三點可參考：
> 1. maximizes impact - 最大化影響
>> 效果團隊是否應該削減產品功能以提高網頁加載時間？
>> Ans: 如果他們只是優化網站速度指標，那麼這個決定可能是一個yes，但如果他們優化更高級別的產品指標，它將更有討論的地方（更有可能與公司的預期影響相一致）。

> 2. actionable metric - 可操作的指標
>> * 其指標的變化是可由團隊所付出的努力來解釋。
>> * eg. 通過 A/B 測試，我們可以由註冊頁面上的更改或新功能推出來解釋可操作指標的變化。

> 3. responsive yet robust - 反應靈敏。
>> 一個響應式指標的快速回應，可以反饋操作團隊其給定的修改是正面還是負面的，以便您的團隊作為之後的參考。

### Instrument Everything to Understand What’s Going On - 監測一切以掌握全局

* 效能監測機制
> eg. 錯誤何時開始，最新代碼部署的時間，身份驗證服務的網絡流量，每個帳戶在各個時間點上的身份驗證嘗試次數以及可能更多的信息

* Etsy 使用 Graphite 這個系統進行即時的系統資訊視覺化支持靈活的實時圖形化，還有使用一個稱為 StatsD 的函式庫來蒐集指標資料。而通過將這些指標與程式碼部署時間進行視覺化的關聯，他們能夠很快地發現某個部署失敗的時間。
* Google，網站可靠性工程師使用一個名為Borgmon的監控系統來收集，統計和繪製指標，並在檢測到異常時發送警報。 
* Twitter 構建了 Observability 分佈式平台，每分鐘收集，存儲和呈現 1.7 億個指標。
* LinkedIn 開發了 inGraphs 圖形分析系統，可讓工程師查看網站儀表板，隨時間比較指標，並設置基於閾值的警報。
* 開源監測工具：Graphite，StatsD，InfluxDB，Ganglia，Nagios 和 Munin。

### Internalize Usefal Numbers - 內化有用的數字

* 有用數字的知識提供了一個寶貴的捷徑，知道在哪裡投資心力可以獲得最大化收益。
* 這些數字幫助您建立更直觀的關於在哪裡指導努力最大化您的槓桿。它們允許你做快速推理決策所需的心理數學和回歸計算。其他可能有助於內部化或至少有現成的數字包括：
> 1. 註冊用戶數，每週活躍用戶和每月用戶數
> 2. 每秒請求的數量
> 3. 存儲的資料量和總容量
> 4. 每天寫入和訪問的數據量
> 5. 支持給定服務所需的服務器數量
> 6. 不同服務或端點的吞吐量
> 7. 交通增長率
> 8. 平均網頁加載時間
> 9. 跨產品的不同部分的流量分佈
> 10. 跨網絡瀏覽器，移動設備和操作系統版本的流量分佈

* eg. MySQL的顧問時常幫助客戶調整資料庫的設定，他們會記錄一些有用的數字，比如說一般來說一次查詢應該可以多快，他們就可以知道現在這個資料庫是否有問題。

* 當你想知道幾個功能中哪一個可能更有價值，例如，一個功能是否可以做得更好？或一個指標是否正常？暫時放下手邊的工作，考慮這些情境是否反覆地出現，以及一些有用的數字或測試方法是否有助於回答這些問題。如果是這樣，請花一些時間收集和內化數據。

### Be Skeptical about Data Integrity - 對資料完整性保持懷疑的態度

* 使用數據來支持你論述的效果是強大的。
> 正確的度量標準可以劃分辦公室政治，思考偏見和產品方針，從而快速解決討論。
> 不幸的是，錯誤的度量可以做同樣的事情 - 災難性的結果。
> 這意味著我們必須小心如何使用數據。

* Google的一個反直覺教訓是，所有數據都可能被濫用，人們會按照他們想要解釋的方式來解釋數據。
> * 選擇容易測量或不甚相關的指標來說明發生了什麼的錯誤
> * 搞混了數據間的因果關係
> * eg. 我們可以看到頁面瀏覽量持續增長，並因此慶祝了瀏覽量的增長 - 但是很大一部分新的請求只是來自一個部署了自動抓取產品數據的機器人。

* 開發團隊有可能會針對產品進行一些實驗，並記錄用戶互動以收集不同的指標。數據最初看起來是可以接受的，甚至團隊沒謹慎的確認資料正確性然後就將注意力轉移至他處。一兩個星期後，當他們開始分析數據時，他們意識到它已被錯誤記錄或某些關鍵行為未被跟踪。當他們開始修復日誌記錄時，幾個星期的迭代時間被浪費了 - 所有這些都是因為他們沒有主動投資數據的準確性。

* 鑑於指標的重要性，投資努力確保您的數據準確是高槓桿。以下是一些可用於提高數據完整性的信心的策略：
> 1. 記錄數據，以免事後證明它是有用的
> 2. 構建工具以更快地迭代數據準確性
> 3. 編寫端到端整合測試以驗證整個分析流水線
> 4. 快速檢查收集的數據
> 5. 當一個數據看起來怪怪的，提前瞭解原因

* 確保您的數據可靠。唯一比沒有數據更糟糕的是擁有正確數據的錯覺。

### Summary

* Measure your progress - 衡量你的進度
* Carefully choose your top-level metric - 請謹慎選擇您的首要指標
* Instrument your system - 量測你的系統
* Know your numbers - 瞭解你的數字
* Prioritize data integrity - 優先確保資料的完整性

## Objective (客觀事實)

* 讓數字／資料說話，以科學方式實際的解決問題

## Reflective (主觀感受) 

* 現在公司常用工時 (or T-shirt size) 來評估一個 task ，只是一直在思考是否有其他更佳的衡量方式

## Interpretive (有何啟發)

* 資料的力量是強大的，所以我們更必須小心地使用，需當心是把雙面刃！

## Decisional (具體實踐)

* 個人化看板


[#The Effective Engineer 讀書會](https://softnshare.wordpress.com/portfolio/packageeffectiveengineer/)
