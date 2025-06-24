# 測試   
---
最後更新: 2025/06/24

更新日誌:
- 2025/06/24 初次提交
---
## 目的

- 驗證程式是否如預期般運作
- 與原有程式環境隔離/分開
- 具有對 最小單位/離散型式/模組化 偵錯
- 使快速定位程式出錯的位置，從早期開始發現問題，降低修復成本

---

## 單元測試 Unit Testing
- [在Replit上做單元測試練習](https://youtube.com/playlist?list=PLSgUBfi51ule4k_MAJC-sHqrO3N4nSokc&si=5xummwhAfOQnSsWw)   
使用《 The machine that changed the world 》的部分片段說明軟體複雜性及單元測試的重要性，並使用Replit上做Python單元測試的練習教學，實際Demo簡單的小時轉分鐘函數，檢查hours變數是否為int, float和轉換是否如預期般的運作: 1小時 = 60分鐘   
不過這是2022年的影片，Replit UI 已做了許多更動


## 手動測試 Manual Testing
- [如何寫手動測試的測試案例](https://www.youtube.com/watch?v=MMa4AVdBCZY)   
1. 開頭就將測試案例區分為三種類型
    - Positive: 有效輸入行為流程
     - Negative: 無效輸入行為流程
     - Destructive: 破壞性行為，測試系統負載
2. 測試案例的結構/組成的元素:   
    - ID: 通常與專案有關且唯一，個人認為比較像是UUID   
        e.g.: BOW-01
    - Summary: 簡短描述，但不會太抽象   
        e.g.: 驗證加入願望清單功能
    - Preconditions: 可選的元素，執行前的條件   
        e.g.: 使用者需要先登入   
    - Steps: 操作步驟流程   
        e.g.: 1. 開啟網站 2. 選擇商品 3. 加入願望清單    
    - Postconditions: 可選的元素，恢復原狀  
        e.g.: 從清單移除商品    
    - Expected Result: 預期結果     
        e.g.: 顯示成功訊息，且商品已加入願望清單中  
    - Actual Result: 實際結果   
        e.g.: 期望與預期結果相符，反之，可能存在錯誤    
    - Status: 結果狀態  
        e.g.: 成功, 失敗
3. 撰寫格式     
    有時候會簡化 2. 的結構或使用不同的欄位名稱，例如使用輸入、輸出  
    這部分就要與團隊夥伴取得共識
4. 撰寫原則     
    - 不依賴其他案例
    - 清楚、獨立、可重複執行
    - 內容準確且易懂
5. 常見錯誤
    - 摘要太抽象: 確實描述驗證何種操作  
        e.g.: 驗證願望清單 -> 驗證加入商品至願望清單
    - 無法點擊的連結:   
        e.g.: google.com -> [Google](https://www.google.com/)
    - 過度詳述: 對於顯而易見的功能，過度詳述    
        e.g.: 點擊商品描述下方的購買按鈕旁的願望清單按鈕 -> 點擊 願望清單 按鈕
    - 缺乏必要細節: 對於技術說明的部分，添加實際操作的步驟  
        e.g.: 開啟開發者模式檢查 mobile view ->     
        開啟開發者模式檢查mobile view:  
        Step1. 打開瀏覽器選項       
        Step2. 更多工具     
        Step3. 開發人員工具 


## 框架
- [unittest](https://docs.python.org/3/library/unittest.html)
- [pytest](https://docs.pytest.org/en/stable/)

## 
- [runoob-python](https://www.runoob.com/python/python-exceptions.html)