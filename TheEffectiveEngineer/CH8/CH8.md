# Part 3: Build Long-Term Value

# CH8. Balance Quality with Pragmatism - 務實地平衡產出品質
## 摘要

### Introduction

* ***Bobby Johnson, a former Director of Engineering at Facebook***, claims that: 
> Thinking in terms of ***[ right and wrong ]*** isn’t a very accurate or useful framework for viewing the world. Instead of right and wrong, I prefer to look at things in terms of ***[works and doesn’t work]***. 

### Establish a Sustainable Code Review Process - 建立可持續的代碼審查流程

* Code Review 的好處是：
> 1. Catching bugs or design shortcomings early - 早早發現 bug 或設計缺陷
>> 在 2008 年的一份研究指出，通過設計和代碼審查，平均可去除 85％ 程式碼撰寫後所遺留的錯誤。
> 2. Increasing accountability for code changes - 增加修改程式碼時的自我要求
> 3. Positive modeling of how to write good code - 積極將"如何寫好代碼"這件事模式化
> 4. Sharing working knowledge of the codebase - 分享代碼庫的工作知識
> 5. Increasing long-term agility - 增加長期敏捷性

* 如何避免審核程式碼花太多時間：
> * 採用 Pair Programming
> * 程式碼提交後再審核
> * 只審查核心基礎架構的程式碼，eg. 只審查業務邏輯 (Model) 的和控制器 (Controller) 代碼，向用戶呈現Web界面 (View) 的代碼不需要審核
> * 多審核新進員工的程式碼
> * 使用代碼審核工具，eg. GitHub, Phabricator
> * 使用Lint自動檢查語法，eg. ESLint, JSHint
> * 自行實驗找出一個適合團隊的審核方式

### Manage Complexity through Abstraction - 通過抽像化來管理複雜性

* MIT 教授丹尼爾·傑克遜在其著作 "軟件抽象" 中說道：『選擇正確的抽象化，程式編寫將自然從設計開始流動發展，模組將具有小而簡單的介面，並且將更能方便的添加新功能而不需進行大範圍的程式碼重構；相對的，如果選擇了錯誤的抽象化，程式編寫將是一系列令人討厭的驚喜，界面將變得醜陋且笨拙，因為他們被迫適應意想不到的互動，甚至最簡單的變化將很難做到。』

* 正確的抽象化能有下列三種產出上的幫助：
> * It reduces the complexity of the original problem into easier-to-understand primitives - 降低複雜度，使之更易被理解
> * It reduces future application maintenance and makes it easier to apply future improvements - 降低未來的維護成本並能更簡單的被擴充
> * It solves the hard problems once and enables the solutions to be used multiple times - 解決的一個困難的問題且解法能被重複使用

* 抽象化也是有過度投資的問題。

* 怎樣是個好的抽象化：
> * easy to learn - 容易學習
> * easy to use even without documentation - 即使沒有文檔也容易使用
> * hard to misuse - 難以濫用
> * sufficiently powerful to satisfy requirements - 足夠強大以滿足要求
> * easy to extend - 容易擴展
> * appropriate to the audience - 適應受眾

* 如何思考抽象化的幾個想法：
> * 從工作中的函式庫或 GitHub 上尋找熱門的專案，閱讀他們的文件，然後深入理解他們的程式碼，並嘗試擴展它們。
> * 查看像Google，Facebook，LinkedIn和Twitter等技術公司的開源專案，了解為什麼像Protocol Buffers，Thrift，Hive和MapReduce這樣的抽像化對它們的業務增長是不可或缺的。
> * 研究由Parse，Stripe，Dropbox，Facebook和Amazon Web Services所開發的 API，並找出開發人員能夠輕鬆地在其平台之上建造其應用的原因。同時研究一下技術社群裡，有些 API 為什麼不討人喜歡！

### Automate Testing - 自動測試

![AutomateTestingErrorRate](https://github.com/adennis1984/BookClub/blob/master/TheEffectiveEngineer/CH8/AutomateTestingErrorRate.png?raw=true "AutomateTestingErrorRate")

* 自動化測試的優點：
> * 如圖一所示，減少錯誤的發生。
> * 減少重複性的測試工作，因此我們可以通過編程方式快速運行大量分支來驗證程式的正確性。
> * 工程師對自己工作產出的品質會更加負責。
> * 工程師會更有自信地執行大範圍的程式碼重構。 

* 較於幾個月甚至幾年後才來補測試，工程師寫程式碼時同時寫測試程式才是最佳的時刻！
* 從 leverage 的角度來說，追求所有的程式都要有 100% 的程式碼涵蓋率是沒有意義，在關鍵的核心部分要求即可！
* 虛擬程式的工程總監Kartik Ayyar解釋： “一旦人們真正開始運行這些單元測試並將它們進行整合時，他們才真的開始看到它節省了多少時間。

### Repay Technical Debt - 償還技術債

* 技術債指的是提高代碼庫的健康程度和品質所必需的所有延遲工作，如果不解決這些問題，將會減慢我們的開發速度。
* 維基百科的發明者 Ward Cunningham 在1992年的會議文章中提出了這個術語：『第一次的程式碼撰寫通常都是在累積債務，這債務會逐步的加速發展，但只要重構就能立即償還！當債務沒有償還時，危機發生。花在不完全正確的代碼上的每一分鐘都是該債務的利息。就像金融債務，如果一直不償還我們技術債務的本金，就意味著我們必須花費越來越多的時間和精力來償還債務所累積的利息，而不是創造價值。』
* 高效率的工程師不是盲目地處理所有的技術債，而是花費他們有限的時間在代碼庫中高度被使用的部分中以最高槓桿力的代碼來償還債務，這需要最少的時間來解決。這些改進對您的努力產生最大的影響。

### Summary
* Establish a culture of reviewing code - 建立一個審查代碼的文化
* Invest in good software abstractions to simplify difficult problems - 投資於良好的軟體抽象化以簡化困難的問題
* Scale code quality with automated testing - 使用自動測試來擴展程式碼品質
* Manage your technical debt - 管理你的技術債

## Objective (客觀事實)

* 四個面向探討問題
> * Code review
> * Abstraction
> * Auto Testing
> * Technical Debt

## Reflective (主觀感受) 
* 架構這件事果然很重要，讓複雜的核心功能抽象化成簡單的操作讓團隊成員正確的去執行！
* 注意技術債的累積是很辛苦的，卻很容易被摧毀啊！
* 在時間壓力的權衡之下，要能有條件地累積技術債！

## Interpretive (有何啟發)
* 

## Decisional (具體實踐)

* 

## 問題
* MVC 作者只針對 MV 做 code review，大家的看法呢？

[#The Effective Engineer 讀書會](https://softnshare.wordpress.com/portfolio/packageeffectiveengineer/)
