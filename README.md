# 以大型語言模型結構化法院判決書 - 以金融詐欺為例 (Structuring Court Judgments with Large Language Models - A Case Study of Financial Fraud Judgments)

[![Made with Python](https.svg)](https://www.python.org/)

[cite_start]這是一個使用大型語言模型（LLM）技術，對台灣金融詐欺案件的法院判決書進行自動化資訊抽取的專案。專案源於國立中山大學資訊管理學系的碩士論文 [cite: 4, 5, 8]。

## 專案簡介 (Introduction)

[cite_start]在數位時代，金融詐欺犯罪日益猖獗，已成為影響全球經濟與社會的嚴重問題 [cite: 44, 45, 51, 52][cite_start]。要有效預防犯罪，深入理解犯罪者的行為模式至關重要，而法院判決書正是獲取這些資訊最可靠的來源 [cite: 45]。

[cite_start]然而，台灣的法院判決書內容繁瑣、文字艱澀，不僅一般民眾難以閱讀，即使是專業人士也需要花費大量時間消化 [cite: 45, 54, 55]。

[cite_start]本研究旨在解決這個問題，我們結合了**正規表示法 (Regular Expressions)** 與**自然語言處理 (NLP)** 技術，並應用 **Llama 3 大型語言模型**，開發一個能自動化解析判決書、提取關鍵資訊的方法 [cite: 46, 56, 58]。

## 研究動機 (Motivation)

* **資訊獲取困難**：判決書的非結構化特性，使其難以進行大規模的數據分析。
* **預防犯罪需求**：期望透過對犯罪模式的分析，為執法單位和金融機構提供有效的防詐策略。
* **提升司法透明度**：將艱澀的法律文件轉化為易於理解的結構化數據，有助於公眾了解司法實務。

## 技術與方法 (Methodology)

本研究的流程主要分為資料收集、特徵提取與模型應用三個階段：

1.  **資料收集 (Data Collection)**：
    * [cite_start]搜集與金融詐欺相關的法院判決書作為原始資料庫 [cite: 32]。

2.  **特徵提取 (Feature Extraction)**：
    * **正規表示法**：利用正規表示法快速且精準地提取格式較為固定的資訊，例如：
        * [cite_start]違反法條 (Violated Laws) [cite: 46, 58]
        * [cite_start]法院地點 (Court Locations) [cite: 46, 58]
        * [cite_start]被告姓名 (Defendant's Name) [cite: 46]
    * [cite_start]**大型語言模型 (Llama 3)**：針對內容較複雜、無固定格式的段落，如「犯罪過程」，利用 LLM 進行語意理解與資訊萃取 [cite: 46, 58]。

3.  **模型優化 (Model Optimization)**：
    * [cite_start]**少量學習 (Few-Shot Learning, FSL)**：由於硬體資源限制，我們採用 FSL 技術，在有限的範例下訓練模型以理解判決書的上下文 [cite: 46, 61]。
    * [cite_start]**模型壓縮**：為適應有限的 GPU 容量，對模型進行了壓縮，以在效率與準確性之間取得平衡 [cite: 46, 61]。

## 主要成果 (Key Features & Results)

本研究成功實現了從判決書中自動提取以下關鍵特徵：

* **違反法條**：識別案件所涉及的具體法律條文。
* **犯罪地點**：定位犯罪行為發生的地理位置。
* [cite_start]**被告資訊**：提取被告的姓名、教育程度、職業與經濟狀況 [cite: 46, 78]。
* [cite_start]**犯罪過程**：結構化並摘要呈現完整的犯罪手法與流程 [cite: 46, 77]。

[cite_start]透過**文本相似度分析** [cite: 38] [cite_start]評估，模型生成的結果與原始判決書內容具有高度一致性，證明了本方法的可行性 [cite: 78]。

## 限制與未來展望 (Limitations & Future Work)

雖然本研究取得了初步成功，但仍存在以下挑戰與未來可行的方向：

* [cite_start]**硬體資源限制**：有限的 GPU 資源影響了模型的規模與訓練效率 [cite: 46, 60]。
* [cite_start]**法律專業知識**：研究團隊缺乏法律背景，可能影響對判決書細微語意的理解 [cite: 46, 60]。

**未來工作將著重於**：
1.  [cite_start]**優化模型效率**：探索更輕量化的模型或更有效率的演算法 [cite: 46, 62]。
2.  [cite_start]**跨領域合作**：加強與法律專業人士的合作，提升資訊提取的準確性與深度 [cite: 46, 62]。
3.  **擴大應用範圍**：將此技術應用於更多類型的法律文件，為法律科技 (LegalTech) 領域做出更大貢獻。

---
*本專案由 許承弘 (Cheng-Hung Hsu) 在指導教授 楊淯程 博士 (Dr. Yu-Chen Yang) 的指導下完成。