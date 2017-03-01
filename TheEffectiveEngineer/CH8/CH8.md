# Part 3: Build Long-Term Value

# CH8. Balance Quality with Pragmatism - 以實用主義來平衡產出的品質
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


* 

* 
> *

### 

### Summary

* 
* 

## Objective (客觀事實)

* 

## Reflective (主觀感受) 

* 

* 

## Interpretive (有何啟發)

* 

## Decisional (具體實踐)

* 


[#The Effective Engineer 讀書會](https://softnshare.wordpress.com/portfolio/packageeffectiveengineer/)
