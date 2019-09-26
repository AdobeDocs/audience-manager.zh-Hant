---
description: '使用以人為本的目的地，將第一方受眾細分傳送至以人為本的環境。 這些環境是屬於一個實體的封閉生態系統，控制其中顯示的內容。 這些平台包括Facebook等社交平台，以及依賴客戶帳戶個人化顯示內容的其他平台。 '
seo-description: '使用以人為本的目的地，將第一方受眾細分傳送至以人為本的環境。 這些環境是屬於一個實體的封閉生態系統，控制其中顯示的內容。 這些平台包括Facebook等社交平台，以及依賴客戶帳戶個人化顯示內容的其他平台。  '
seo-title: 基於人員的目標概觀和使用案例
solution: Audience Manager
title: 概觀與使用案例
translation-type: tm+mt
source-git-commit: 6093def9c5853572c064a4e398d5e328bcb9d181

---


# 概觀與使用案例 {#overview-use-cases}

使用 [!DNL People-Based Destinations] 將第一方受眾細分傳送至以人為本的環境。 這些環境是屬於一個實體的封閉生態系統，控制其中顯示的內容。 這些平台包括社交平台， [!DNL Facebook]以及依賴客戶帳戶個人化顯示內容的其他平台。

## 概述 {#overview}

[!DNL People-Based Destinations] 可讓您針對線上和離線資料套用區段，以根據雜湊識別碼(例如 [電子郵件地址](people-based-destinations-prerequisites.md#hashing-requirements)或電話號碼)建立觀眾區段。 然後，您可以將這些區段傳送至「圍牆花園」, [!DNL Facebook]例如，您可以在社交平台上鎖定受眾。 [!DNL People-Based Destinations] 可協助您：

* 根據雜湊的電子郵件位址，鎖定平台 [!DNL Facebook]中的離線和線上受眾；
* 補充Audience manager現有的裝置和Cookie定位功能；
* 免除與第三方資料上線解決方案相關的成本；
* 免除開發自訂資料上線工作流程的相關成本；
* 在無Cookie環境中鎖定受眾；
* 借由刪除與客戶ID相符的電子郵件地址，以鎖定受眾。

您可以使 [!DNL People-Based Destinations] 用來區隔和定位未瀏覽您網站的高價值客戶，或停止定位已離線轉換的客戶。 此外，您還可 [!DNL Profile Merge Rules] 以運用線下第一方資料與線上第一方資料（包括來自其他Adobe Experience cloud解決方案的客戶資料）相結合，以最佳化您的社交媒體廣告成果。

![pbd-overview](assets/pbd-overview.png)

## Availability {#availability}

[!DNL People-Based Destinations] 是Audience manager的進階整合。 請連絡您的Adobe代表，以利用這項優質功能。

## 為何應使用以人為本的目的地 {#why-use}

**從Audience manager管理整個受眾細分，為客戶提供一致的跨通道體驗。**

不透過Audience manager在以人為本的通道中啟動受眾細分，會導致客戶造訪網站時所見與其動態消息（例如）之間的體驗脫節 [!DNL Facebook] 。 跨通道擁有一致的定位，可以增加廣告收入，同時最佳化廣告支出。

**在以人為本的通道中觸及受眾，而不需使用專屬的資料入門解決方案或自訂工作流程來傳送受眾。**

The more "traditional" way of targeting audiences across people-based channels involves you having to export your customer data in a format accepted by the platform that you want to advertise on, and then using the platform's dedicated data onboarding method to bring your customer data to your advertiser account. This is all manual work that you need to do for each platform that you want to advertise on. Additionally, different platforms may have different data format requirements, making the process even more tedious.

![pbd-overview](assets/pbd-diagram.png)

Through [!DNL People-Based Destinations], Audience Manager helps you centralize your customer data, build audience segments, and activate them across multiple people-based channels. You can do this all from within the Audience Manager UI, avoiding the additional work of manually uploading data to each platform, saving you valuable time in the process.

**Create and activate audience segments from purely offline profiles.**

[!DNL People-Based Destinations] solve the issue that previously, you could only activate audience segments based on device activity. With , you can create segments from purely offline data from your own , and activate them in people-based platforms. [!DNL People-Based Destinations][!DNL CRM]Additionally, you can correlate your offline data with device data that you already have in Audience Manager.

**Leverage Audience Manager's data governance and privacy controls to safely handle customer data.**

[!DNL People-Based Destinations] 要求您僅使用不可逆轉的雜湊識別碼。 This reduces the risk associated with manually uploading customer data into each destination platform.

## 使用個案 {#use-cases}

To help you better understand how and when you should use , here are two sample use cases that Audience Manager customers can solve by using this feature.[!DNL People-Based Destinations]

### Use Case #1 {#use-case-1}

線上零售商想透過社交平台接觸現有客戶，並根據先前的訂單向他們展示個人化優惠。 With , the online retailer can ingest hashed email addresses from their own  to Audience Manager, build segments from their own offline data, and send these segments to the social platforms they want to advertise on, optimizing their advertising spending.[!DNL People-Based Destinations][!DNL CRM]

### Use Case #2 {#use-case-2}

An airline has different customer tiers (Bronze, Silver, and Gold), and wants to provide each of the tiers with personalized offers via social platforms. 該公司使用Audience manager分析網站上的客戶活動。 不過，並非所有客戶都使用該航空公司的行動應用程式，其中有些客戶尚未登入該公司網站。 公司對於這些客戶的唯一識別碼是會籍ID和電子郵件地址。

若要跨社交媒體和類似以人為本的通道鎖定客戶，他們可以將客戶資料從雜湊的電子郵件地址當成識別碼，從 [!DNL CRM] Audience Manager中將其帶入客戶資料。

接下來，他們可以結合線下資料和現有的線上活動特徵，以建立新的受眾細分，並透過這些細分進行鎖定 [!DNL People-Based Destinations]。
