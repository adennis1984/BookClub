# Part 2: Execute, Execute, Execute

# CH6. Validate Your Ideas Early and Often - 儘早驗證你的想法

## 摘要

### Introduction

* 在第4章中，我們了解到，投資迭代速度有助於我們完成更多的事情。在本章中，我們將針對如何操作進行更細部的討論！

### Find Low-Effort Ways to Validate Your Work - 找到輕量的方式來驗證工作

* 小機器人蒐集紅球例子：
> * 機器人的前進方向會因為前軸和後軸的馬達速度的微小變化，輪胎胎面的差異以及場地表面上的輕微凸起等的因素而以一個角度漂移。路徑越長，這些小錯誤越複雜，機器人越不可能到達球。
> * 一個更可靠的方法是機器人向前移動一點點，然後重新檢查相機並校正機器人的前進方向，並重複，直到到達目標。
> * 每個迭代周期越短，我們就越能更快的從錯誤中學習。反之，迭代周期越長，不正確的假設和錯誤就越有可能複合成更嚴重的錯誤。

* 在專案－特別是大型專案上，我們應該不斷地問自己：*我可以先花一小部分的時間來收集一些數據，並驗證我正在做什麼工作嗎？*

* DropBox 的例子：
> * Drew Houston (DropBox 創辦人) 先拍一個四分鐘影片作為他的MVP。休斯頓展示了他的產品的幾個版本 - 將文件同步顯示在 Mac，Windows PC和網頁上。隔天，Dropbox beta 版本的註冊使用者從 5k 增加到 75k，休斯頓知道他正在做對的事情。 

* 驗證你想法的一種方法是花費10％的精力構建一個小的，可運作的原型(prototype)。
> * 根據您的項目目標，您可以使用您的原型來測量代表性工作負載的性能，比較重寫到原始模塊的模塊的代碼佔用空間，以及評估添加新功能的容易程度。
> * 構建快速原型的成本在較大項目的方案中並不算太多，但是如果它早期表現出問題，則它生成的數據可以為您節省大量的痛苦和努力，

* Asana 的例子：
> 有一天，Asana - 一個構建協作和任務管理的軟體公司，正在考慮是否要在他們的登入畫面上添加一個新的Google註冊按鈕，而目地是為了增加使用者的註冊率。 
> 他們先增加一個假註冊按鈕來驗證了這個想法 - 而不是直接開發整個註冊流程：當訪問者點擊按鈕時，會出現一個彈出消息，“謝謝你感興趣 - 功能即將推出。”
> Asana 工程師測量了幾天的點擊率，而且在確認數據顯示這有助於增加註冊率後才開始建立完整註冊流程。

* 投入少量工作來收集數據以驗證你專案的假設和目標，從長遠來看，你會為自己節省大量的浪費。

### Continuously Validate Product Changes with A/B Testing - 使用 A/B 測試持續驗證產品修改

* 歐巴馬競選經費籌募的例子：
> 在20個月的時間裡，經過嚴格 A/B 測試的募款電子郵件而獲得的線上捐贈占了奧巴馬總競選經費 6.90 億美元的決大部分 - 這效益非常值得團隊花時間的投資。

* A/B 測試提供了一種科學的方法來測量實驗變因的影響，同時控制其他變化變因，好讓我們評估產品的影響。
* A/B 測試不僅僅幫助您決定要啟動哪個版本 - 即使你相信變因一定會提高我們度量的指標，A/B 測試也會告訴你這變因實際上效果有多好。
* 量化這種改善方式可以檢視繼續投資在同一領域是否有意義。例如，投資了資源在一件大型產品上，其留客率卻只有1％的提升，這意味著您可能會在其他地方找到更多的槓桿力。

* Etsy 的例子：
> 他們假設 “顯示使用者更多的市場產品會降低跳出率” ，然後進行實驗將使用者感興趣的類似產品顯示在商品列表頁的最上方，並且分析使用者行為是支持還是拒絕該假設（實際上， 它將跳出率降低了近10％）。 
> 基於該實驗，團隊了解到他們應該將更多市場產品的圖像合併到他們的最終設計中。

* A/B 測試框架：
> * 免費：Etsy’s feature-flagging API, Vanity, Genetify, 和 Google Content Experiments. 
> * 付費：Optimizely, Apptimize, Unbounce, and Visual Website Optimizer.

* Google 的例子：
> * Google 可以對微小的細節運行測試。例如，他們分析了在搜索結果鏈接中使用的41種藍色陰影，選擇正確的陰影使 Google 每年的廣告收入額外增加2億美元。
> * 即使表面上微乎其微的 0.01％ 的收入增長，年收入為 310 億美元的公司則為 310 萬美元。

### Beware the One-Person Team - 當心一人團隊

* 一人團隊
> * 有時，為了擺脫溝通成本，管理人員或技術主管會將指整個團隊將拆分成個別的單人團隊，以便他們可以獨立處理較小的任務，並使協調更容易。
> 一些組織會強調工程師必須保有專案項目的所有權 - 這可以激勵工程師自己工作，希望最大限度地提高他們的晉昇機會。雖然，也有一些工程師只是單純更喜歡獨立工作。
> * 雖然在一人團隊上不會有任何內在溝通上的錯誤，但它確實帶來了額外的風險，如果不解決，可能會降低你的成功機會。
> 首先，它增加了獲取反饋的過程的摩擦 - 你需要反饋，以幫助驗證你正在做什麼工作。
> 例如，除非代碼審閱者在你的團隊中工作並共享了你的項目情境，否則很難獲得有關代碼審查的良好反饋。
> * 而且，如果你不設置反饋循環，很有可能直到專案結束你還不知道自己已經走錯了方向，還很自鳴得意地覺得它趨近完美 - 你會浪費很多的精力在做不必要的事情。
> * 另一個風險是，當遭遇專案瓶頸時一人團隊因無人可以討論及溝通，更有可能因此而身陷低潮泥淖而無法自拔。

* 一些增加專案成功率的策略建議：
> * Be open and receptive to feedback - 開放和接受反饋
> * Commit code early and often - 提前且經常提交程式碼
> * Request code reviews from thorough critics - 嚴格的程式碼審查
> * Ask to bounce ideas off your teammates. - 向團隊成員尋求反饋
> * Design the interface or API of a new system first - 先設計新系統的介面或API
> * Send out a design document before devoting your energy to your code - 在將你的精力投入到程式碼前先發出設計文件
> * If possible, structure ongoing projects so that there is some shared context with your teammates - 可能的話，與團隊成員一同建構專案
> * Solicit buy-in for controversial features before investing too much time - 投入開發之前，先釐清有疑義功能

### Build Feedback Loops for Your Decisions - 為你的決策建構反饋循環

* "你做出的任何決定...都應該有一個反饋循環。否則，你只是...猜。"  ~ Facebook 工程總監 Nimrod Hoofien

### Summary

* Approach a problem iteratively to reduce wasted effort - 迭代地處理問題，以減少浪費的工作量
* Reduce the risk of large implementations by using small validations - 使用小型驗證來降低大型實作的風險
* Use A/B testing to continuously validate your product hypotheses - 使用 A/B 測試來持續驗證你的產品假設
* When working on a solo project, find ways of soliciting regular feedback - 即使在個人專案上工作也要找到定期反饋的方法
* Adopt a willingness to validate your decisions

## Objective (客觀事實)

* 工程師獨立作業是有獨立作業的風險的

## Reflective (主觀感受) 

* Google 有錢就是任性 XD
* 一人團隊那段看了好有感覺，網頁開發來說一直覺得前後端就是該一起做不然溝通成本好大，之前就有覺得這樣是不是怪怪的，作者就完整地說了這樣的問題！

## Interpretive (有何啟發)

* 做了什麼不是重點，產生了什麼價值才是重點

## Decisional (具體實踐)

* 不能只是老是悶著頭做事，還是必須停下來抬起頭，定時地審視自己，才能更確定自己是走在正確的道路上！


[#The Effective Engineer 讀書會](https://softnshare.wordpress.com/portfolio/packageeffectiveengineer/)
