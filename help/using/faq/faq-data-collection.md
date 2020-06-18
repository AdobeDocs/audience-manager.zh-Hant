---
description: 資料收集和整合的常見疑問與問題。
seo-description: 資料收集和整合的常見疑問與問題。
seo-title: 資料收集和產品整合常見問題集
solution: Audience Manager
title: 資料收集和產品整合常見問題集
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; SFTP address; STFP IP address; FTP address
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 96%

---


# 資料收集和產品整合常見問題集{#data-collection-and-product-integration-faq}

資料收集和整合的常見疑問與問題。

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**如何在[!DNL DCS]記錄檔匯出項目中區分來自[!DNL DCS]的傳入流量？**

透過 [!UICONTROL Inbound] 上線的特徵會以 [!UICONTROL Inbound] 填入，其方式與以 [!DNL DCS] 填入的方式相同。有幾種不同的方式可以判斷流量是來自 [!UICONTROL Inbound]：

* 遠端 IP 將設為 68.67.173.18
* 網域 ID 將設為 5325
* 地區將設為 0

<br> 

**您能否提供我可新增至dpm.demdex.net允許清單的IP位址清單？**

很遺憾，恕無法提供。這些 IP 會透過 [!DNL Amazon Web Services] 依地理區域以動態方式指派。因此，[!DNL Audience Manager] 不會控制可指派給此位址的 IP 範圍。

<br> 

**您是否可提供IP位址給我，讓我新增至傳入和傳出sFTP伺服器的允許清單？**

可以，請參閱下文。

| 項目 | 位址 |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**[!UICONTROL DIL]/[!DNL Analytics]資料整合**&#x200B;的程式碼放置和頁面載入要求為何？

若要將 [!DNL Analytics] 資料帶入 [!DNL Audience Manager]，請在 `s_code` 模組之後、`s.t()` 函數&#x200B;*之前*&#x200B;載入 [!UICONTROL DIL]。例如，請依下列順序放置程式碼，或確定程式碼已依照以下順序載入：

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL] 模組

3. [!DNL Analytics] `s.t()` 函數

根據最佳實務，請透過下列 2 種方法之一設定您的 [!DNL Audience Manager] 與 [!DNL Analytics] 整合：

* 直接將 [!UICONTROL DIL] 放入 `s_code` 中。

* 透過 [!DNL Adobe Experience Platform Launch] 或 [!DNL Adobe DTM] 處理 [!UICONTROL DIL] 和 `s_code`。

請參閱 [Data Integration Library (DIL) API](../dil/dil-overview.md)。

<br> 

**為什麼我的[!DNL Analytics]變數沒有在[!DNL Audience Manager]事件呼叫中出現？**

這通常會發生在以下情況中：

* 您透過標籤管理系統處理 [!UICONTROL DIL]，而該系統是以非同步方式載入頁面上的其他程式碼元素。
* `s.t()` 函數在 [!UICONTROL DIL] 之前載入。

<br> 

**哪些[!DNL Analytics]版本可搭配[!UICONTROL DIL]使用？**

您必須使用 [!DNL Analytics] 20.2 版 (或更新版本) 和 [!DNL Adobe AppMeasurement AS] 程式庫 3.5.2 版 (或更新版本) 才能使用 [!UICONTROL DIL]。如果您不知道您的 [!DNL Analytics] 或 [!DNL AppMeasurement] 版本，請查看從頁面發出的 [!DNL Analytics] 呼叫。版本資訊如下所示：

此客戶使用 [!DNL Analytics] 24.4 版：

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

此客戶使用 [!DNL AppMeasurement] 3.5.2 版：

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**如果我不是[!DNL Analytics]客戶，可以收集頁面資料嗎？**

是。即使您未使用 [!DNL Analytics]，[!UICONTROL DIL] 模組仍可協助您收集頁面資料。正確設定後，[!UICONTROL DIL] 便可從向以下項目擷取其相關資料：

* 中繼標籤
* URL 和 URL 標頭
* 搜尋引擎類型
* 關鍵字

此外，用戶端可部署簡單的站上物件，並填入您希望 [!UICONTROL DIL] 收集資料的索引鍵值配對。這可讓您新增和移除網站上的特定受眾資料點，而不需進行任何 [!DNL Audience Management] 更新。請與您的合作夥伴解決方案代表合作，正確進行此設定，並確保 [!DNL DIL] 模組正確參考頁面物件。

<br> 

**[!UICONTROL DIL]可以從[!DNL Google Analytics]中收集資料嗎？**

是。[!UICONTROL DIL] 可以收集某些 [!DNL Google Analytics] (GA)元素並將該資料傳遞至 [!DNL Audience Manager]。請參閱：

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**我可以從[!DNL Audience Manager]中取得原始資料嗎，其精細度為何？**

可以，[!DNL Audience Manager] 可向您提供針對我們在您的詳細目錄中看到的使用者所收集的資料。其中包括：

* 由 [!DNL Audience Manager] 指派的不重複使用者 ID (UUID)
* 特徵和區段 ID
* 未使用的訊號
* 時間戳記
* 頁面 URL

<br> 

**我想要收集一個網站的資料，並透過不同網站的 DFP 定位使用者。如果我不想從那個位置收集資料，是否需要將程式碼部署在其他屬性上？**

不會。如果不需要在第二個網站上收集資料，您就不需要在那裡部署 DIL。只要您透過 DFP 存取第二個網站的詳細目錄，就可以透過 DFP 使用從初始網站和目標收集的資料。

<br> 

**哪個第三方資料提供者是最佳選擇？**

每個提供者提供的內容均獨一無二，因此答案取決於您要尋找的內容。我們可以啟用重疊報表 (免費)，幫助您瞭解哪個提供者最適合您。

<br> 

**[!DNL Audience Manager]如何設定 Cookie 及將變數傳遞至 DFP？**

[!DNL Audience Manager] 會設定 2 個 Cookie：其中一個會將區段變數傳送至 DFP 廣告標籤，另一個則會設定我們的不重複使用者 ID (UUID)，而 DFP 也會讀取此 ID。將 UUID 新增至廣告標籤，表示我們可以執行使用者層級的報表和受眾探索。

<br> 

**是否可傳送轉換漏斗中使用者觸及點的相關 DSP 資訊？**

是。我們可以傳送漏斗資料，但是 DSP 必須具備使用這些資料的技術能力。DSP 必須確認其可以處理多個區段。如果無法，我們可能需要建立特定區段，以根據使用者的轉換進度將使用者從其他區段中提取出 (例如已完成步驟 1 和 2，但步驟 3 尚未完成)。您可將這些資訊傳送至 DSP，讓 DSP 可對使用者重新進行定位、將其導向至特定登陸頁面，或顯示特定創意內容。

<br> 

**如何確認透過 FTP 傳送的資料是否已被[!DNL Audience Manager]擷取？**

當副檔名從 `.sync` 變更為 `.processed`，表示已擷取檔案。發生此情況時，檔案會位於擷取佇列中。此外，您的帳戶管理員可確認檔案上傳完畢的時間。

<br> 

**我想測試[DCS API](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)的功能。我傳送了一個事件呼叫，如下所示。這些呼叫中包含[宣告 ID](../features/declared-ids.md)和訊號，而這些 ID 和訊號應會實現我已設定的某些特徵和區段。我可以使用[!UICONTROL General Reports]和[!UICONTROL Trend Reports]來驗證特徵和區段母體是否正在增加嗎？**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

不可以，這個情況下，請勿依賴 [!UICONTROL General Reports] 和 [!UICONTROL Trend Reports]。

報表是根據報表產生時在後端看到的未驗證設定檔記錄 (UUID) 來計算母體。

對 [!DNL DCS] 發出第一次呼叫時，宣告 ID *不會*&#x200B;連結至任何 UUID (也就是用戶端上不存在 [demdex Cookie](hhttps://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html))。[!DNL DCS] 會隨機產生 UUID 並設定 [!DNL demdex] Cookie，然後在回應呼叫中傳遞，但不會將 UUID 傳輸送到後端。

>[!NOTE]
>
>只有在已設定 Cookie 的裝置觸發進一步活動後，產生的 UUID 才會在後端資料儲存區中具體化。

基於這個原因，報表不會反映呼叫中宣告 ID 所觸發的事件。建議您在對 [!DNL DCS] 發出的事件測試呼叫中使用 UUID、ECID (前身為 MID) 或行動裝置 ID。接下來，您可以驗證 [!UICONTROL General Reports] 和 [!UICONTROL Trend Reports] 中的特徵和區段實現。

另請參閱 [Audience Manager ID 的索引](../reference/ids-in-aam.md)。

<br> 

**跨[地區](../api/dcs-intro/dcs-api-reference/dcs-regions.md)同步使用者設定檔需要多久？**

在不同地區間同步使用者設定檔通常需要 24 小時。不過在少數情況下，此程序可能會耗費最多 48 小時。
