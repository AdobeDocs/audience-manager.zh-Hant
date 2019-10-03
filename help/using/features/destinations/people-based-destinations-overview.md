---
description: '使用以人為本的目的地，將第一方受眾細分傳送至以人為本的環境。 這些環境是屬於一個實體的封閉生態系統，控制其中顯示的內容。 這些平台包括Facebook等社交平台，以及依賴客戶帳戶個人化顯示內容的其他平台。 '
seo-description: '使用以人為本的目的地，將第一方受眾細分傳送至以人為本的環境。 這些環境是屬於一個實體的封閉生態系統，控制其中顯示的內容。 這些平台包括Facebook等社交平台，以及依賴客戶帳戶個人化顯示內容的其他平台。  '
seo-title: 基於人員的目標概觀和使用案例
solution: Audience Manager
title: Overview and Use Cases
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# 概觀與使用案例 {#overview-use-cases}

使用 [!DNL People-Based Destinations] 將第一方受眾細分傳送至以人為本的環境。 這些環境是屬於一個實體的封閉生態系統，控制其中顯示的內容。 這些平台包括社交平台， [!DNL Facebook]以及依賴客戶帳戶個人化顯示內容的其他平台。

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

## 概述 {#overview}

[!DNL People-Based Destinations] 可讓您針對線上和離線資料套用區段，以根據雜湊識別碼(例如 [電子郵件地址](people-based-destinations-prerequisites.md#hashing-requirements)或電話號碼)建立觀眾區段。 Then, you can send these segments to "walled gardens" such as , where you can target your audience on the social platforms. [!DNL Facebook][!DNL People-Based Destinations] 可協助您：

* 根據雜湊的電子郵件位址，鎖定平台 [!DNL Facebook]中的離線和線上受眾；
* 補充Audience manager現有的裝置和Cookie定位功能；
* 免除與第三方資料上線解決方案相關的成本；
* 免除開發自訂資料上線工作流程的相關成本；
* Target audiences in cookie-less environments;
* Target audiences by deduplicating email addresses matched to customer IDs.

You can use  to segment and target high value customers who may not visited your website, or stop targeting those who have already converted offline. [!DNL People-Based Destinations]Additionally, you can leverage  to combine your offline first-party data with your online first-party data, including customer data from other Adobe Experience Cloud solutions, to optimize your social media advertising efforts.[!DNL Profile Merge Rules]

![pbd-overview](assets/pbd-overview.png)

## Availability {#availability}

[!DNL People-Based Destinations] 是Audience manager的進階整合。 Please contact your Adobe representative to take advantage of this premium feature.

## 為何應使用以人為本的目的地 {#why-use}

**從Audience manager管理整個受眾細分，為客戶提供一致的跨通道體驗。**

不透過Audience manager在以人為本的通道中啟動受眾細分，會導致客戶造訪網站時所見與其動態消息（例如）之間的體驗脫節 [!DNL Facebook] 。 跨通道擁有一致的定位，可以增加廣告收入，同時最佳化廣告支出。

**在以人為本的通道中觸及受眾，而不需使用專屬的資料入門解決方案或自訂工作流程來傳送受眾。**

更「傳統」的跨人類通道鎖定受眾方式包括，您必須以平台所接受的格式匯出客戶資料，然後使用平台專用的資料登入方法將客戶資料匯入廣告商帳戶。 這些都是您需要針對每個要廣告的平台進行的手動工作。 此外，不同平台可能有不同的資料格式需求，使程式變得更加繁複。

![pbd-overview](assets/pbd-diagram.png)

Through , Audience Manager helps you centralize your customer data, build audience segments, and activate them across multiple people-based channels. [!DNL People-Based Destinations]You can do this all from within the Audience Manager UI, avoiding the additional work of manually uploading data to each platform, saving you valuable time in the process.

**Create and activate audience segments from purely offline profiles.**

[!DNL People-Based Destinations] solve the issue that previously, you could only activate audience segments based on device activity. With , you can create segments from purely offline data from your own , and activate them in people-based platforms. [!DNL People-Based Destinations][!DNL CRM]Additionally, you can correlate your offline data with device data that you already have in Audience Manager.

**Leverage Audience Manager's data governance and privacy controls to safely handle customer data.**

[!DNL People-Based Destinations] requires that you only use irreversibly hashed identifiers. 這可降低手動將客戶資料上傳至每個目標平台的相關風險。

觀看以下影片，瞭解使用時的資料流程 [!UICONTROL People-Based Destinations]。

>[!VIDEO](https://video.tv.adobe.com/v/28968/?captions=chi_hant)

## 使用個案 {#use-cases}

為協助您更清楚瞭解應如何及何時使用 [!DNL People-Based Destinations]，以下是Audience manager客戶可使用此功能解決的兩個範例使用案例。

### Use Case #1 {#use-case-1}

線上零售商想透過社交平台接觸現有客戶，並根據先前的訂單向他們展示個人化優惠。 有了 [!DNL People-Based Destinations][!DNL CRM] ，線上零售商可以將雜湊的電子郵件地址從自己的Audience Manager中收錄、從自己的離線資料建立區段，並將這些區段傳送至他們想要廣告的社交平台，以最佳化其廣告支出。

### Use Case #2 {#use-case-2}

航空公司有不同的客戶層級（銅、銀和金），並希望透過社交平台為每個層級提供個人化優惠。 該公司使用Audience manager分析網站上的客戶活動。 不過，並非所有客戶都使用該航空公司的行動應用程式，其中有些客戶尚未登入該公司網站。 公司對於這些客戶的唯一識別碼是會籍ID和電子郵件地址。

若要跨社交媒體和類似以人為本的通道鎖定客戶，他們可以將客戶資料從雜湊的電子郵件地址當成識別碼，從 [!DNL CRM] Audience Manager中將其帶入客戶資料。

接下來，他們可以結合線下資料和現有的線上活動特徵，以建立新的受眾細分，並透過這些細分進行鎖定 [!DNL People-Based Destinations]。
