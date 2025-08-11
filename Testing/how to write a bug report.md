
# How to write a bug report     如何編寫 bug 報告 / 開票

Below is a short summary of what to include for each component of a full bug report.    
以下是完整 bug 報告的每個組成部分應包含的內容的簡短摘要。

## Clear Title  清楚的標題
A moderator should be able to understand what the bug report is about from the title alone.     
版主應該能夠僅從標題中理解錯誤報告的內容。

## One bug per report   每個報告一個 bug
**Report one bug in a single report**. If you put in more than one bug it may be overlooked.    
在單個報告中報告一個 bug。如果您輸入了多個 bug，則可能會被忽略。

## Actual results  實際結果 
This section should **expand on the title by stating** the behaviour observed when the issue occurs.    
此部分應通過說明問題發生時觀察到的行為來擴展標題。

## Expected results  預期結果
The Expected Results section should **state how** the app should behave according to its intended behaviour.    
預期結果部分應說明應用程式應如何根據其預期行為運行。

- E.g: The authorisation phase completes successfully, the user is logged into the newly created account and redirected to the home page of the app.    
例如：授權階段成功完成，用戶登錄到新創建的帳戶並重定向到應用程式的主頁。

## Steps to reproduce   重現步驟：
The Steps to Reproduce section should list each step required to reproduce the bug in **chronological order**.  
重現步驟部分應按時間順序列出重現 bug 所需的每個步驟。

## Severity of the bug  錯誤的嚴重性
We use 5 categories to identify the severity of the bug.    
我們使用 5 個類別來確定 bug 的嚴重性。
- **Critical** -  The bug prevents **critical functionality** within the app from working. This includes crashing, freezing for which no workaround is possible and **a fix is required immediately**.  
嚴重 -  該 bug 會阻止應用程式中的關鍵功能正常工作。這包括崩潰、凍結，無法解決，需要立即修復。   
- **High** - The bug affects major functionality within the app from working. However, high priority bugs can be avoided with a workaround.     
高 - 此 bug 影響應用程式內的主要功能無法正常工作。但是，可以通過解決方法避免高優先順序錯誤。    
- **Medium** - The bug does not cause a failure and does not interfere with the fluent work of the system and programs. **It has an easy workaround.**  
中 - 該 bug 不會導致失敗，也不會干擾系統和程序的流暢工作。它有一個簡單的解決方法。  
- **Low** - **The bug does not affect functionality or data, or require a workaround**. It is a result of non-conformance to a standard that does not impact productivity (e.g. typing errors/aesthetic inconsistencies, etc.). 
低 - 錯誤不會影響功能或數據，也不需要解決方法。 這是由於不符合不影響工作效率的標準（例如，鍵入錯誤/美學不一致等）的結果。   
- **Usability** - A **suggestion** that would improve how an app is understood, experienced or used efficiently.    
易用性 - 改進應用程式理解、體驗或有效使用方式的建議。   

## Device and Operating System  設備和作業系統
Each bug report must include details of the specific device and operating system you used during the test to identify the bug.  
每個 bug 報告都必須包含您在測試期間用於識別 bug 的特定設備和作業系統的詳細資訊。  

## Other Notes/Error Messages   其他說明/錯誤消息
Include necessary and relevant evidence to show the problem you are describing.     
包括必要的相關證據，以證明您所描述的問題。
- Evidence includes: screenshots, videos, crash or console logs (for crashes).       
證據包括：螢幕截圖、影片、崩潰或控制台日誌（用於崩潰）。      
- Crashes and freezes should always include a video and console/crash logs.   
崩潰和凍結應始終包含影片和控制台/崩潰日誌。     
- Bugs with more than one step to reproduce usually require a video.    
要重現多個步驟的 bug 通常需要影片。     

---
## 參考文獻
- [Bug reporting guidelines](https://testerwork.com/everything-you-want-to-know-about-bug-reporting/)
- [Support Centre](https://gathelp.zendesk.com/hc/en-us)

---
看到這個說明書覺得很好，所以翻成中文存起來