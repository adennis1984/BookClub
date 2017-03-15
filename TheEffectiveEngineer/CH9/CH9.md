# Part 3: Build Long-Term Value

# CH9. Minimize Operational Burden - 最小化操作負擔

## 摘要

### Embrace Operational Simplicity - 擁抱操作簡單性

* 額外的複雜性可能是一個必要之惡 - 但通常，它不是。
* 『當你第一次嘗試解決問題時，你提出的第一個解決方案通常是非常複雜的，大多數人就都因此止步不前了。但如果你持續下去探究這個問題，經過層層的抽絲剝繭姐，你通常會得到一些非常優雅和簡單的解決方案。大多數人只是不願意投入時間或精力罷了。』 - 史帝夫·賈伯斯 

* 過度複雜的架構會在幾個方面影響增加維護成本：
> * Engineering expertise gets splintered across multiple systems - 工程專業知識跨越多個系統
> * Increased complexity introduces more potential single points of failure - 增加的複雜性引入更多的潛在的錯誤風險
> * New engineers face a steeper learning curve when learning and understanding the new systems - 當學習和理解新系統時，新進工程師將面臨更陡峭的學習曲線
> * Effort towards improving abstractions, libraries, and tools gets diluted across the different systems - 改進抽象化結構，函式庫和相關工具的努力會因為橫跨不同的系統而被稀釋

* Pinterest 原本的系統架構是由 MySQL, Cassandra, Membase, Memcache, Redis, Elastic Search, and MongoDB 等技術所組成，隨後將其複雜度調整為 MySQL, Memcache, Redis和Solr，也因此他們通過增加每個服務中的機器數量而不是引入任何新服務，獲得了超過 4 倍的增長！

* 四個值得注意的 high-leverage 的簡單操作情境：
> * 對於一個原型或玩具專案來說，嘗試一種新的程式語言是件好事，但是在新的生產系統中使用它之前要考慮一下。其他團隊成員是否具有該語言的經驗？是容易學習的嗎？是否很難順利地招聘工程師？
> * 新的資料存儲技術的支持者會宣稱他們的系統解決了經過許多實戰測試的關連式資料庫（如MySQL和PostgreSQL）中的問題，但是，在生產中使用這些新的存儲系統之前要先做些研究，了解其他團隊是否已經成功地將它們用於類似範圍的專案，以及他們是否能夠以比更標準的解決方案更低的操作負擔來維護和擴展它們。
> * 當處理一個新問題時，考慮是否重用現有的抽像化或工具將比重新開發新的解決方案更簡單。人們經常會說：『使用正確的工具來做這項工作』，但這會因此增加了現有工具的數量。不斷成長的元件間的複雜性其使用優點是否已經超過了通過標準化的簡單性的好處？
> * 如果您正在處理大量數據，請考慮數據是否實際足夠大，以至於您需要一個分佈式集群，或者是否使用單一的，強大的機器就足夠了。集群比單台機器更難管理和調試。

### Build Systems to Fail Fast - 快速迭代地建構系統

* 不當的錯誤捕捉及錯誤紀錄方式會導致雖然系統能夠正常運行但會因此更難正確地找到問題原因
> * Suppose an analytics program that processes log files simply skips over all corrupted data that it encounters. It’ll be able to continue generating reports, but days later, when customers complain that their numbers are inconsistent, we’ll be scratching our heads and struggling to find the cause.
> * Reflective => 雖然這比喻不太恰當，但我想到了 ***倖存者謬誤***

* A valuable technique for shortening that feedback loop is to make your software fail fast.
* "Failing fast is a nonintuitive technique: ‘failing immediately and visibly’ sounds like it would make your software more fragile, but it actually makes it more robust. Bugs are easier to find and fix, so fewer go into production.” 13 By failing fast, we can more quickly and effectively surface and address issues." - Jim Shore, IEEE, Fail Fast
> * Reflective => 尼采：" ***凡是殺不死我的，都將使我更強壯*** " XDDDD

* **操作概念就是，有錯誤就一層一層往外拋出 (throw)，讓最外面的異常處理程序再處理就好，絕對不要私自吞掉！**
> * Reflective => npm jwt 就有這個問題，出 error 程式就停了也沒有 callback 回來，也沒資料回傳，就只能等 timeout ...

* 當Web請求逾時，應用程序作為 MySQL 共享連接池 (shared connection pool) 的一部分卻沒有被正確地重置。當下一個不確定的Web請求進入並重用相同的連接時，其第一個查詢將獲得針對超時請求的響應。
* Memcached 的過期時間以秒為單位表示，但最多只有30天。任何大於30天（2,592,000秒）的數字被解釋為 UNIX 時戳 (從1970年開始算)，也就是設定馬上過期。
> * => 學習了！

* 構建系統快速失敗可能是一個非常高槓桿的活動。它通過更快更直接地處理有問題的問題，有助於減少維護和程式碼除錯的時間。

### Relentlessly Automate Mechanical Tasks - 持續地自動化機械任務

* 每次你做一些機器可以做的事情，不斷問自己這是否可以自動化？不要讓你努力工作付出的結果卻只是讓這些人工任務來虛耗你的光陰。

### Make Batch Processes Idempotent - 使批次處理等冪

* 等冪
> * 使批次處理更容易維護和更有彈性地故障的一種技術是使它們等冪。
> * 無論運行一次還是多次，冪等過程都會產生相同的結果。
> * 無副作用 (side effect)

* A failed process might still be holding onto a global lock or have emitted partial output; designing the process so that it knows how to handle these inconsistent states can reduce the amount of manual handholding required later. Make each process either fail entirely or succeed entirely.
> * Reflective => transaction?

* 等冪特性的優點：以更頻繁而不是嚴格必要的速率運行不頻繁的進程，以更快地暴露問題。
> * Reflective => Idempotent 的概念看起來好像 functional programming XD

### Hone Your Ability to Respond and Recover Quickly - 磨練你的能力以快速回應和回復

* Netflix 的工程師們建立了一個名為 Chaos Monkey 的系統，隨機殺死其自己的基礎設施中的服務。他們不是花費資源讓服務能順利活著，而是積極地對自己的系統造成破壞。事實證明，這個策略實際上使他們的基礎設施更加健壯。針對重大故障的最佳防禦是經常失敗。當 Netflix 依賴於其雲服務的 Amazon Web Services 遭受重大故障時，Netflix 能夠逃脫服務中斷，而其他公司，如Airbnb，Reddit，Foursquare，Hootsuite 和 Quora 遭受了多個小時的停機時間。
* Netflix 的方法說明了降低運營負擔的強大策略：開發快速恢復的能力。不管我們做了多少努力，事情總是會在某些時候出錯。 
* Netflix，Google和Dropbox都假設意外和不期望的情況會發生。他們練習他們的失敗情況，以加強他們迅速恢復的能力。他們認為，當事情一切順利時，最好主動計劃和編寫腳本，而不是在不受控制的情況下爭取解決方案。

* 最大限度地減少我們自己的運營負擔意味著我們也可以將更多的時間投入到更有意義的方式來推動影響力

### Summary

* Do the simple thing first
* Fail fast to pinpoint the source of errors
* Automate mechanics over decision-making
* Aim for idempotence and reentrancy
* Plan and practice failure modes

## Reflective (主觀感受) 
* 我們開發產品總是不斷的設想用戶需求然後不斷的增加新功能，但，那都不是用戶要的啊！
* [一窩蜂驅動開發](https://blog.chunfuchao.com/?p=656)

## Interpretive (有何啟發)
* KISS - Keep It Simple and Stupid - is always the best practice.

## Decisional (具體實踐)
* 保持簡單思維，持續不斷問自己，有沒有更簡單的做法！ 
* 永遠先假設自己會犯錯，犯錯不是重點，重點是要能快速的偵錯並能快點回復原來的狀態！

## 問題
* sharding VS scale out
* retry VS reentrancy

[#The Effective Engineer 讀書會](https://softnshare.wordpress.com/portfolio/packageeffectiveengineer/)
