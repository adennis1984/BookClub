# CH1. 綁定模型與實作

## Objective (客觀事實)

### 模式：MODEL-DRIVEN DESIGN

* 如果「整個程式設計或其核心部分」沒有與「領域模型」相對應，那個這個模型就是沒有價值的，軟體正確性也值得懷疑。
* MODEL-DRIVEN DESIGN（模型驅動設計）不在將『分析模型』與『程式設計』分離，而是尋求一種能夠『滿足這兩方面需求』的單一模型。
* 綁定（bind）模型和應用程式是切實可行的。
  > 模型和設計的綁定需要的是在『分析和程式設計階段』都能發揮良好作用的模型

### 建構範式（paradigm）和工具支持

* 為了使 MODEL-DRIVEN DESIGN 發揮作用，一定要在『可控制的範圍內』嚴格保證模型與設計之謙的一致性。要實踐這種一致性，必須要利用軟體工具所支持的建模範式（modeling paradigm），他可以在程式中『直接建立模型中的對應概念』。
![ModelParadigmDesign](./190517.jpg?raw=true "ModelParadigmDesign")

* 只有用程式碼表達模型概念時，物件設計的『真正突破之處』才彰顯出來。Java 和許多其他工具都允許建立『直接反應概念物件模型』（conceptual object models）的物件和關係。

### 模式：HANDS-ON MODELERS

* 如果編寫程式的人認為自己沒有必要對模型負責，或者不知道如何讓模型為應用程式服務，那麼這模型就和程式沒有任何關聯。
* 如果建模人員不參與程式實作的過程，那麼對程式實作的約束就沒有切身的感受。
* HANDS-ON MODELERS 不等於團隊成員不能有自己的專業角色。
  > 但是如果把 MODEL-DRIVEN DESIGN 中密切相關的『建模』和『實作』這兩個過程分離，則會產生問題。

### Question?

* P55. 採用外觀（facade）模式可以更容易地存取這些介面
* P57. 使用者模型和設計/實作模型（the user model and the design/implementation model）

## Reflective (主觀感受)

* 要能有意識地站在對方的角度透過 UBIQUTIOUS LANGUAGE 進行討論溝通
  
## Interpretive (有何啟發)

* 你的理解就是我的理解嗎？我們真的講的是同一個事情嗎？

## Decisional (具體實踐)

* 期勉自己能真的走在「軟體產品能夠在『完全理解核心領域』的基礎上提供『豐富的功能』」的道路上。
  