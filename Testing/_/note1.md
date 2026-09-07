

---
## 測試計畫生命週期 
::: mermaid
graph TD
    TP[Test Plan 制定] --> TC[Test Case 撰寫] --> EX[測試執行] --> BR[Bug 回報]
    subgraph 測試階段
        UT[Unit Test] --> IT[Integration Test] --> ST[System Test] --> AT[Acceptance Test]
    end
    TP --> UT
    TP --> IT
    TP --> ST
    TP --> AT
:::

---
---

### [測試計畫 Test Plan](https://ithelp.ithome.com.tw/articles/10331123)      
最先制定的總體計畫，確立範圍、目標、方法、資源、時程與風險因應等  
- **e.g.: 5W2H** (Why, what, who, when, where, how, how cost)   
- 目的、範圍、類型(測試類型、測試案例)、資源(環境&工具)、指派(人員)、排程、風險與對策、交付物(報告&溝通)等

#### 參考文件 Reference Docs:
- 專案計劃（Project Plan）: 時程、里程碑、資源
- 產品需求規劃書（PRD）: 需求清單、驗收準則 / 測甚麼?
    - 需求追蹤矩陣（Requirement → Test Case）：每條 PRD 的需求要對應至少一個 Test Case（表格或 CSV）
- 設計文件（Design Doc / Spec / API Spec / DB Schema）: 技術細節 / 怎麼測?
    - 設計對應測試：API spec 的每個 endpoint 要對應 Integration Test 與 API 測試案例

#### 常用工具
- [Confluence](https://www.atlassian.com/software/confluence) / Notion
- Google Drive / Office 365

### [測試案例 Test Case](https://ithelp.ithome.com.tw/articles/10332525)    
測試計畫完成後、**測試執行前**，把測試計畫列出的功能與場景等需求切分成具體可重複執行的案例，用來驗證功能是否符合    
預期可能會有的bug發想與設計，也是設計測試案例的一環，像是邊界情況、異常情況    
- e.g.: ID (CaseID, RequirementID) 、摘要(描述名稱、對象、內容)、優先級、嚴重度、前置條件、測試資料、測試類型、操作步驟、後置條件、期望結果、實際結果、狀態、自動化建議、估計耗時、測試者、環境、附件/Logs、備註 

#### 常用工具
- [TestRail](https://www.testrail.com/): 可和 Jira 集成; [範例](https://ithelp.ithome.com.tw/articles/10333220)
- for Jira: Xray / Zephyr
- TestLink


### [開缺陷票 Ticket / Bug report](https://ithelp.ithome.com.tw/articles/10333817)  
::: mermaid
graph TD
    NEW[New] --> ASSIGN[指派給開發者]
    ASSIGN --> FIX[修復中]
    FIX --> RETEST[測試人員重測]
    RETEST --> CLOSE[關閉（通過）]
    RETEST --> REOPEN[重新開啟（未通過）]
    REOPEN --> ASSIGN
:::

實際依照測試案例**執行時/執行後**，發現實際結果≠預期結果時，紀錄Bug內容
- e.g.: 摘要、實際結果、預期結果、重現步驟、設備/環境、狀態、嚴重性、附件/證據、指派人員

#### 常用工具
- [Jira](https://www.atlassian.com/software/jira)
- for Git: Github Issues / GitLab Issues


---
---

## 測試階段 / 層次
越前面越靠近開發者，反之靠近使用者  

### 單元測試 Unit Testing
對程式最小可測單元（函式、方法、類別）進行測試  
- 獨立、自動化、快速執行、[發現早期錯誤](https://medium.com/@loverjersey/%E8%81%8A%E8%81%8A%E6%B8%AC%E8%A9%A6%E5%B7%A6%E7%A7%BB-c8fcfaf4cb70)
    - 通常會包含測試案例 Test case
- 通常是 開發者 / 測試工程師 執行
- e.g.: unittest, Assert, 解析電文, github CI/CD push merge前, TDD   

### 整合測試 Integration Testing    
測試不同模組或服務間的互動、整合
- 模組整合、接口測試、驗證協同、自動化、模擬
    - 資料流、API通訊、資料庫
- 通常是 開發者 / QA 執行
- e.g.: Postman, pytest+requests, 解析電文後整合進資料庫    

### 系統測試 System Testing 
對整個系統做端對端測試，而不再是小單元間的  
- 測試全系統、功能驗證、性能測試、壓力測試、安全測試、回歸測試
    - 當測試範圍擴大時，會開始從工程師的角度切換成使用者角度
    - 回歸測試作為策略/類型，可用於各個階段
- 通常是 QA / 測試工程師 執行
- e.g.: Selenium, 功能驗證, 回歸測試 

### 驗收測試 Acceptance Testing 
驗證滿足客戶或最終使用者需求，於開發完成後、交付前執行  
- 用戶參與、測試場景、準則和標準、最終交付
- 通常是 使用者 / PM / QA 執行
- e.g.: 使用者手動測試, UAT

### 實務中的情形
- 會在階段中導入 [Happy path/ flow](https://en.wikipedia.org/wiki/Happy_path)
- [敏捷開發 Agile software development](https://zh.wikipedia.org/zh-tw/%E6%95%8F%E6%8D%B7%E8%BD%AF%E4%BB%B6%E5%BC%80%E5%8F%91): 快速迭代、自動化測試、即時反饋，是價值觀和原則的集合，常見的框架有[Scrum](https://www.scrum.org/resources/scrum-guide), [Kanban](https://learn.microsoft.com/zh-tw/devops/plan/what-is-kanban)


---
---

## 測試策略 Testing Strategy
### [回歸測試](https://ithelp.ithome.com.tw/articles/10327072)
確保對軟體更改後，先前正常運作的部分不會受到影響
- 確保穩定性、省時間和成本、快速回饋
- 初期自動化成本、維護成本高、執行時間
### 分層規則、優先級、KPI、風險對策


## 測試方法 Testing Methods
可使用的測試技術、策略或過程

### 黑箱測試 Black Box Testing: 使用者角度，不考慮程式內部  
- 適用 整合測試、系統測試、驗收測試
- e.g.: 等價類劃分法、邊界值分析法、錯誤推測法、因果圖法、判定表法、正交試驗法、功能圖法、場景法
### 白箱測試 White Box Testing / 透明盒測試 glass box testing / 結構測試 structural testing: 基於程式內部邏輯   
- 適用 單元測試、整合測試、系統測試
- e.g.: 控制流測試、資料流控制、分支測試、語句覆蓋、判定覆蓋、MC/DC、主要路徑測試、路徑測試
### 灰箱測試

---
---

## 測試內容 / 範圍
### [例外處理](https://ithelp.ithome.com.tw/articles/10325430)
在軟體中[處理異常或意外情況的機制](https://www.runoob.com/python/python-exceptions.html)    
- 簡潔易維護、增強穩定性和可靠性、提高UX及安全性、減少錯誤發生、保護數據完整性
### 功能清單、業務流程、邊界值、安全項目

---
---

## 測試執行 Execution
人員、工具、環境、CI原則、測試案例、規範

### 手動測試

### 自動化測試

#### 常用工具
- Selenium
- Cypress
- Playwright
- Appium

### API測試

#### 常用工具
- Postman + Newman
- Rest Assured (Java)、 requests / pytest (Python)
- Pact / contract testing（契約測試）

### 單元測試

#### 常用工具
- JUnit / pytest / Jest / Mocha / NUnit

---
---

## [測試結果與反思](https://ithelp.ithome.com.tw/articles/10334475)   
### 測試報告 Test Report
詳細記錄測試過程中的所有關鍵信息
- 報告摘要 Report Summary
- 測試環境 Test Environment
- 測試計畫和策略 Test Plan and Strategy
- 測試執行 Test Execution
- 問題和缺陷 Issues and Defects
- 測試指標 Test Metrics
- 測試日誌 Test Log
- 總結和建議 Summary and Recommendations

### 測試指標 Test Metrics
量化測試案例以評估測試的效率和品質
- 通過的測試案例數 Passed Test Cases
- 失敗的測試案例數 Failed Test Cases
- 未執行的測試案例數 Not Run Test Cases
- 測試覆蓋率 Test Coverage
- 測試通過率 Pass Rate
- 平均測試執行時間 Average Test Execution Time
- 問題數量 Number of Issues
- 嚴重性分布 Severity Distribution
- 測試執行進度 Test Execution Progress
- 測試自動化覆蓋率 Test Automation Coverage


### 問題報告 Issue Reports
分析問題清單(問題、缺陷、改進建議)
- 問題描述
- 重要性、優先級
- 問題狀態: New / In Progress / Resolved / Closed
- 詳細信息: 日期、人員、問題定位、屬性、附件、相關的測試案例
- 相關紀錄: 測試日誌、錯誤訊息、異常堆棧、版本信息



---
---
## list
- [Software Testing terms complete glossary](https://www.softwaretestinghelp.com/software-testing-terms-complete-glossary/)
- [ISTQB](https://glossary.istqb.org/zh_CN/search?term=&exact_matches_first=true)
- [Glossary of Testing Terms](https://reqtest.com/en/knowledgebase/glossary-of-testing-terms/)
- [Software Testing Glossary: One-Stop Guide for 100+ Testing Terms](https://www.lambdatest.com/learning-hub/glossary)
- [QA 概念養成](https://ithelp.ithome.com.tw/users/20103826/ironman/6736)
    - [推薦文章](https://ithelp.ithome.com.tw/articles/10328115)
    - [測試認證](https://ithelp.ithome.com.tw/articles/10337398)
- [github source](https://github.com/stars/hate20130527/lists/qa)