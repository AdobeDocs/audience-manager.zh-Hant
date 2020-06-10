---
description: 常見的資料收集與整合問題與問題。
seo-description: 常見的資料收集與整合問題與問題。
seo-title: 資料收集與產品整合常見問答集
solution: Audience Manager
title: 資料收集與產品整合常見問答集
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; SFTP address; STFP IP address; FTP address
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 1%

---


# 資料收集與產品整合常見問答集{#data-collection-and-product-integration-faq}

常見的資料收集與整合問題與問題。

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**如何在記錄檔匯出中區分[!UICONTROL DCS]傳入流[!UICONTROL DCS]量和流量？**

透過登入的 [!UICONTROL Inbound] 特徵會以 [!UICONTROL Inbound] 填入方式填入，與填入方式相同 [!UICONTROL DCS]。 有幾種不同的方法可以判斷流量來自 [!UICONTROL Inbound]:

* 遠程IP將設定為68.67.173.18
* 網域ID將設為5325
* 地區將設為0

<br> 

**您能否提供我可新增至dpm.demdex.net允許清單的IP位址清單？**

不幸的是，我們不能。 這些IP會依地理區域、透過動態指派 [!DNL Amazon Web Services]。 因此，不 [!DNL Audience Manager] 會控制可指派給此位址的IP範圍。

<br> 

**您是否可提供IP位址給我，讓我新增至傳入和傳出sFTP伺服器的允許清單？**

是的，請參閱下面。

| 項目 | 地址 |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**「[!UICONTROL DIL]/資料整合」的程式碼放置和頁面載[!DNL Analytics]入需求為何？**

要將數 [!DNL Analytics] 據導入 [!DNL Audience Manager]，請在模 [!UICONTROL DIL] 塊之後載入， `s_code` 在函式之 *前*`s.t()` 載入。 例如，請依下列順序放置程式碼，或確定其已載入：

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL] 模組

3. [!DNL Analytics] `s.t()` 函式

作為最佳實務，請設定您 [!DNL Audience Manager]- [!DNL Analytics] 與下列2種方法的整合：

* 直 [!UICONTROL DIL] 接放入 `s_code`。

* 服務 [!UICONTROL DIL] 和 `s_code` 穿透 [!DNL Adobe Experience Platform Launch] 或 [!DNL Adobe DTM]。

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**為什麼我的[!DNL Analytics]變數在事件呼叫中[!DNL Audience Manager]遺失？**

這通常發生在：

* 您可透過標 [!UICONTROL DIL] 簽管理系統提供服務，該系統會以非同步方式載入頁面上的其他程式碼元素。
* 函式 `s.t()` 在之前載入 [!UICONTROL DIL]。

<br> 

**哪些版本[!DNL Analytics]可搭配使用[!UICONTROL DIL]?**

您必須使 [!DNL Analytics] 用20.2版（或更新版本）和 [!DNL Adobe AppMeasurement AS] 3.5.2版（或更新版本）的程式庫才能使用 [!UICONTROL DIL]。 如果您不知道您的或版 [!DNL Analytics] 本 [!DNL AppMeasurement] ，請檢查 [!DNL Analytics] 從頁面發出的呼叫。 下列版本資訊：

此客戶使 [!DNL Analytics] 用24.4版：

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

此客戶使 [!DNL AppMeasurement] 用3.5.2版：

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**如果我不是客戶，可以收集頁面資[!DNL Analytics]料嗎？**

是。即使 [!UICONTROL DIL] 您未使用，模組仍可協助您收集頁面資料 [!DNL Analytics]。 正確設定後，可 [!UICONTROL DIL] 以從以下位置擷取資料：

* Meta標籤
* URL和URL標題
* 搜尋引擎類型
* 關鍵字

此外，客戶可部署簡單的Onsite物件，並填入您要收集資料的金 [!UICONTROL DIL] 鑰值配對。 這可讓您新增和移除網站上的特定受眾資料點，而不需進行任何 [!DNL Audience Management] 更新。 請與您的合作夥伴解決方案代表合作，以正確設定此設定，並確 [!DNL DIL] 保模組正確參照頁面物件。

<br> 

**可以[!UICONTROL DIL]從中收集資料嗎[!DNL Google Analytics]?**

是。[!UICONTROL DIL] 可以收集 [!DNL Google Analytics] 某些(GA)元素並將該資料傳遞至 [!DNL Audience Manager]。 請參閱:

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**我可以從中取得原始資[!DNL Audience Manager]料，其粒度為何？**

是的，可 [!DNL Audience Manager] 以提供您所收集的資料，以供我們在您的庫存中看到的使用者使用。 其中包括:

* 由指派的唯一使用者ID(UUID) [!DNL Audience Manager]
* 特徵和區段ID
* 未使用的信號
* 時間戳記
* 頁面URL

<br> 

**我想要收集一個網站的資料，並透過不同網站的DFP鎖定使用者。 如果我不想從另一個位置收集資料，是否需要將程式碼部署在其他屬性上？**

不會。如果不需要在第二個網站上收集資料，您不需要在那裡部署DIL。 只要您透過DFP存取第二個網站的庫存，就可以透過DFP使用從初始網站和目標網站收集的資料。

<br> 

**什麼是最佳的協力廠商資料提供者？**

每個提供者都會為表格提供獨一無二的內容，因此答案取決於您要尋找的內容。 我們可以啟用重疊報告（免費），幫助您瞭解哪家供應商最適合您。

<br> 

**如何設[!DNL Audience Manager]定Cookie並將變數傳遞至DFP?**

[!DNL Audience Manager] 設定2個Cookie: 其中一個會傳送區段變數至DFP廣告標籤，另一個則會設定我們的唯一使用者ID(UUID),DFP也會讀取此ID。 將UUID新增至廣告標籤表示我們可以執行使用者層級的報告和觀眾搜尋。

<br> 

**我們是否可傳送有關使用者到達轉換漏斗的點數的DSP資訊？**

是。我們可以發送漏斗資料，但是DSP必須具備使用它的技術能力。 DSP必須確認它們可以處理多個段。 如果無法，我們可能需要建立特定區段，以根據使用者的轉換進度將使用者從其他區段中拉出（例如，已完成步驟1和2，但不是步驟3）。 您可能想要將此資訊傳送至DSP，讓他們可以重新鎖定使用者、將他們導向至特定的登陸頁面，或顯示特定的創作素材。

<br> 

**我要如何確認透過FTP傳送的資料是否被擷取[!DNL Audience Manager]?**

副檔名從變更為時，已選取 `.sync` 檔案 `.processed`。 發生此情況時，檔案會位於擷取佇列中。 此外，您的帳戶管理員可確認檔案已上傳。

<br> 

**我想測試[DCS API的功能](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)。 我傳送的事件呼叫，如下所示。 這些呼叫包[含Declared ID](../features/declared-ids.md)和訊號，這些ID和訊號應可實現我已設定的某些特性和區段。 我是否可以使用[!UICONTROL General Reports]和[!UICONTROL Trend Reports]來驗證特徵和群體人口是否在增加？**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

不，不要依賴於 [!UICONTROL General Reports] 和 [!UICONTROL Trend Reports] 本案。

報表會根據未驗證的描述檔記錄(UUID)來計算人口族群，這些記錄在產生報表時會在後端看到。

在對的第一次呼 [!UICONTROL DCS]叫時，所宣告的ID *不會連結* 至任何UUID(即用戶端上 [不存在demdex Cookie](hhttps://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) )。 隨機 [!UICONTROL DCS] 產生UUID並設定 [!DNL demdex] Cookie，然後在回應呼叫中傳遞它，但不會將UUID傳送到後端。

>[!NOTE]
>
>只有在設定Cookie的裝置觸發進一步活動後，產生的UUID才會在後端資料儲存中實作。

因此，報表不會反映呼叫中已宣告的ID所觸發的事件。 建議您在對的事件測試呼叫中使用UUID、ECID（先前稱為MID）或行動裝置ID [!UICONTROL DCS]。 然後，您可以驗證和中的特徵和區 [!UICONTROL General Reports] 段實現 [!UICONTROL Trend Reports]。

另請參閱Audience [Manager ID的索引](../reference/ids-in-aam.md)。

<br> 

**使用者設定檔跨地區同步需要多[久](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

使用者設定檔在不同地區間同步通常需要24小時。 不過，在少數情況下，此程式最多需要48小時。
