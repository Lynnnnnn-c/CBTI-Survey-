==Quiz==
呈現 CBTI 問題（QuestionCard）
接收使用者答案
根據答題情況進行 跳題邏輯處理
完成後計算結果，並顯示結果頁
==Component/QuestionCard ===
處理單一題目（Question）的 UI - 進度顯示、Scale題滑桿樣貌、單選題...etc
===Component/ResultsDisplay =====
做完測驗完結果頁的UI
＊記得把課金幹話刪掉 但我也不介意大家課金給我
====Component/quizData=====
CBTI 問題資料庫定義所有問題、問題格式（單選、Scale、Mutiscale題組）、權重、問題所屬面向
定義CBTI 類型人格總表
==Component/MultiScaleQuestion===
處理多子題量表（Multi-scale）的樣貌定義每個級距的分數
====Component/RankingQuestion====
進階處理Muti-scale 題組計分邏輯，例如同一題目測量用戶偏向依賴社群或客觀資料，組子題1是偏向測社群依賴度 分數是5到1, 另一個子題是測客觀資料依賴度 分數是1到5
(1) 整體社群情緒與討論熱度	非常關鍵	5 高度影響	4	有影響	3 稍有影響	2 完全不影響	1
(2) 自己建立的模型（鏈上與宏觀數據、回測)或資金分配原則	非常關鍵	1 高度影響	2 有影響	3 	稍有影響	4 完全不影響	5 
子題們會在同一個頁面，Scale都是非常關鍵～完全不一影響，因此這份檔案會將子題(1)tag為C, (2)tag為O, 若為O 分數擷取方式即為 6-1
＊＊＊＊＊理論上 <MultiScaleQuestion /> 和 <RankingQuestion /> 這兩個可以合併成一個元件（？）我應該會偏好這樣處理但我一類組我不確定＊＊＊
==== Component/MultiScaleQuestion ===
核心邏輯處理元件，計算加權後分數總和，例如
if第九題>4(a.k.a 投資期間三個月以下，一律分到"S"，其餘繼續往下測驗，最後這dimension 分數總和以15分為分水嶺再去區分S or L
***每個Dimension的邏輯都不一樣不太能通用＊＊＊
===/entities/QuizResult===
定義CBTI 測驗後要儲存的結果資料格式 資料庫給他串起來之後可以結合你們那邊在做的User Tagging for personalization strategy



