---
description: 常見資料收集與整合問題與問題。
seo-description: 常見資料收集與整合問題與問題。
seo-title: 資料收集與產品整合常見問題
solution: Audience Manager
title: 資料收集與產品整合常見問題
uuid: fa8e79f4-99cb-41fd-8a85-d4 f92 d03 c7 a5
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# Data Collection and Product Integration FAQ{#data-collection-and-product-integration-faq}

常見資料收集與整合問題與問題。

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**如何將傳入流量從[!UICONTROL DCS][!UICONTROL DCS]記錄檔匯出中區分開來？**

Traits onboarded via [!UICONTROL Inbound] are populated by [!UICONTROL Inbound] the same way they get populated by [!UICONTROL DCS]. There are a few different ways to tell that traffic came from [!UICONTROL Inbound]:

* 遠端IP將設為68.67.173.18
* DomainId將設為5325
* 地區設為0

<br> 

**可以提供我可以列入dpm. demdex. net名單的IP位址清單嗎？**

不幸的是，我們無法做到。These IPs are assigned dynamically, by geographic region, through [!DNL Amazon Web Services]. As a result, [!DNL Audience Manager] does not control the range of IPs that can be assigned to this address.

<br> 

**可以為我提供IP位址給傳入和傳出FTP伺服器的白名單嗎？**

是的，請參閱下方。

| 項目 | 地址 |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**A[!UICONTROL DIL]/[!DNL Analytics]資料整合的程式碼位置和頁面載入需求為何？**

To bring [!DNL Analytics] data into [!DNL Audience Manager], load [!UICONTROL DIL] after the `s_code` module but *before* the `s.t()` function. 例如，放置程式碼或確定它載入，依照下列順序載入：

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager][!UICONTROL DIL] 模組模組

3. [!DNL Analytics]`s.t()` 函數

As a best practice, set up your [!DNL Audience Manager]- [!DNL Analytics] integration with either of these 2 methods:

* Put [!UICONTROL DIL] directly in the `s_code`.

* Serve [!UICONTROL DIL] and the `s_code` through [!DNL Adobe Launch] or [!DNL Adobe DTM].

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**為甚麼我的[!DNL Analytics]變數因[!DNL Audience Manager]事件呼叫而遺失？**

通常發生於下列情況：

* You serve [!UICONTROL DIL] through a tag management system that loads it asynchronously with other code elements on the page.
* `s.t()` 函數會載入 [!UICONTROL DIL]之前。

<br> 

**哪些版本[!DNL Analytics][!UICONTROL DIL]可搭配使用？**

You must use [!DNL Analytics] version 20.2 (or higher) and the [!DNL Adobe AppMeasurement AS] library version 3.5.2 (or higher) to work with [!UICONTROL DIL]. If you don&#39;t know your [!DNL Analytics] or [!DNL AppMeasurement] version, check the [!DNL Analytics] call that gets made from the page. 版本資訊如下：

This customer uses [!DNL Analytics] version 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

This customer uses [!DNL AppMeasurement] version 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**如果我不[!DNL Analytics]是客戶，可以收集頁面資料嗎？**

是。[!UICONTROL DIL] 模組可協助您收集頁面資料，即使您未使用 [!DNL Analytics]。When set up properly, [!UICONTROL DIL] can capture data from and about:

* 中繼標籤
* URL和URL標題
* 搜尋引擎類型
* 關鍵字

Additionally, clients can deploy a simple onsite object and populate it with key-value pairs that you want [!UICONTROL DIL] to collect data on. This lets you add and remove specific audience data points on your site without any [!DNL Audience Management] updates. Work with your Partner Solutions representative to properly set this up and ensure the [!DNL DIL] module references the page object correctly.

<br> 

**可以[!UICONTROL DIL]收集[!DNL Google Analytics]資料嗎？**

是。[!UICONTROL DIL] 可以收集部分 [!DNL Google Analytics] (GA)元素並傳遞該資料給 [!DNL Audience Manager]。請參閱:

* [GA. SubmitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA. init](../dil/dil-modules.md#ga-init)

<br> 

**我可以從原始資料[!DNL Audience Manager]取得原始資料嗎？**

Yes, [!DNL Audience Manager] can provide you with data collected for users we&#39;ve seen on your inventory. 其中包括:

* The unique user ID (UUID) assigned by [!DNL Audience Manager]
* 特徵和區段ID
* 未使用的訊號
* 時間戳記
* 頁面URL

<br> 

**我想要在一個網站上收集資料，並透過不同網站上的DFP定位使用者。Do I need to deploy code on the other property if I don&#39;t want to collect data from that location?**

不會。如果第二個網站上的資料收集不是必要的，您不需要部署DIL。只要您可以透過DFP存取第二個網站上的存貨，就可以從初始網站使用資料收集，並透過DFP進行定位。

<br> 

**甚麼是最佳第三方資料供應商？**

每個提供者都會為表格提供獨特的內容，因此答案取決於您要尋找的內容。我們可以啓用重疊報告(免費)，協助您瞭解哪個供應商最適合您。

<br> 

**[!DNL Audience Manager]如何設定Cookie並將變數傳遞至DFP？**

[!DNL Audience Manager] 設定Cookie：One send segment variable to the DFP ad tag and one the other set我們唯一的使用者ID(UUID)，這也由DFP讀取。將UUID新增至廣告標記代表我們可以進行使用者層級報告和觀眾發現。

<br> 

**我們可以傳送有關使用者到達轉換漏斗之點數的DSP資訊嗎？**

是。我們可以傳送漏斗資料，但是DSP必須具備技術能力。DSP必須確認可以處理多個區段。如果無法，我們可能需要建立特定區段，根據他們的轉換進度(例如完成的步驟和步驟而非步驟3)來提取使用者之外的區段。您可能想要將此資訊傳送至DSP，以便重新定向使用者、將他們導向特定登陸頁面，或顯示特定創意素材。

<br> 

**如何確認透過FTP傳送的資料已被擷取[!DNL Audience Manager]起來？**

A file has been picked up when the extension changes from `.sync` to `.processed`. 此時，檔案就位於擷取佇列中。此外，您的帳戶管理員也可以確認檔案已上傳。

<br> 

**我想要測試[DCS API](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)的功能。我傳送事件呼叫，如下所示。The calls contain[Declared IDs](../features/declared-ids.md)and signals, which should realize some traits and segments I have already set up. Can I use the[!UICONTROL General Reports]and[!UICONTROL Trend Reports]to verify if the trait and segment populations are increasing?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

No, do not rely on the [!UICONTROL General Reports] and [!UICONTROL Trend Reports] in this case.

報表會根據我們在產生報表時在後端看到的未驗證描述檔記錄(UUID)來計算人口族群。

On a first call to the [!UICONTROL DCS], the declared IDs are *not* linked to any UUID (i.e. no [demdex cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) is present on the client side). The [!UICONTROL DCS] will randomly generate a UUID and set a [!DNL demdex] cookie and pass it on in the response call, but it will not transmit the UUID to the backend.

>[!NOTE]
>
>一旦設定Cookie的裝置將觸發進一步活動，產生的UUID只會在後端資料儲存中實例化。

因此，報表不會反映呼叫中宣告之ID所觸發的事件。We recommend you use UUID, ECID (formerly MID) or mobile device IDs in event test calls to the [!UICONTROL DCS]. Then, you can verify the trait and segment realizations in the [!UICONTROL General Reports] and in the [!UICONTROL Trend Reports].

See also, the [Index of Audience Manager IDs](../reference/ids-in-aam.md).

<br> 

**使用者設定檔在[各地區的同步化需要多久](../api/dcs-intro/dcs-api-reference/dcs-regions.md)？**

使用者設定檔通常需要24小時，才能跨地區同步。但是，在少數情況下，此程序可能需要48小時。
