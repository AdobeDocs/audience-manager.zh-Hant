---
description: 使用以人物為基礎的目的地，將第一方對象區段傳送至以人物為基礎的環境。 這些環境是屬於一個實體的封閉生態系統，該實體控制其中顯示的內容。 其中包括Facebook等社交平台，以及其他依賴客戶帳戶個人化顯示內容的平台。
seo-description: Use people-based destinations to send first-party audience segments to people-based environments. These environments are closed ecosystems belonging to one entity that controls the content that is being displayed within it. They include social platforms such as Facebook, and other platforms that rely on customer accounts to personalize the displayed content.
seo-title: People-Based Destinations Overview and Use Cases
solution: Audience Manager
title: 概述與使用案例
feature: People-based Destinations
exl-id: 2edbda3b-e2a3-4a92-965b-206a21764cc8
source-git-commit: ab3361a0a54a7200d2f0c03a82ae6ef61a755be9
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 0%

---

# 概述與使用案例 {#overview-use-cases}

使用[!DNL People-Based Destinations]將第一方對象區段傳送至以人物為基礎的環境。 這些環境是屬於一個實體的封閉生態系統，該實體控制其中顯示的內容。 包括[!DNL Facebook]等社交平台，以及其他依賴客戶帳戶個人化顯示內容的平台。

>[!IMPORTANT]
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 此處未包含任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

## 概述 {#overview}

[!DNL People-Based Destinations]可讓您對線上和離線資料套用分段，以根據[雜湊識別碼](people-based-destinations-prerequisites.md#hashing-requirements)建立對象區段，例如電子郵件地址。 接著，您可以將這些區段傳送至「圍牆花園」，例如[!DNL Facebook]，藉此在社交平台上鎖定您的對象。 [!DNL People-Based Destinations]可以協助您：

* 根據雜湊電子郵件地址，在[!DNL Facebook]等平台中鎖定離線和線上對象；
* 補充Audience Manager的現有裝置和Cookie鎖定目標功能；
* 消除與第三方資料上線解決方案相關的成本；
* 消除開發自訂資料上線工作流程的相關成本；
* 在無Cookie的環境中鎖定對象；
* 刪除與客戶ID相符的雜湊電子郵件地址，以鎖定受眾。

您可以使用[!DNL People-Based Destinations]來區隔並鎖定可能未造訪過您網站的高價值客戶，或停止鎖定已離線轉換的高價值客戶。 此外，您可以運用[!DNL Profile Merge Rules]將離線的第一方資料與線上第一方資料(包括其他Adobe Experience Cloud解決方案的客戶資料)結合，以最佳化您的社群媒體廣告工作。

![pbd-overview](assets/pbd-overview.png)

## 可用性 {#availability}

[!DNL People-Based Destinations]是進階Audience Manager整合。 請聯絡您的Adobe代表以使用此進階功能。

## 為何您應使用[!UICONTROL People-Based Destinations] {#why-use}

**從Audience Manager內管理整個對象細分，為客戶提供一致的跨頻道體驗。**

若未透過Audience Manager在以人物為基礎的管道中啟用您的對象區段，會導致您的客戶在造訪您的網站時看到的內容與他們在其[!DNL Facebook]摘要中看到的內容之間出現脫節的體驗。 跨頻道保持一致的目標定位，可增加廣告收入，同時最佳化廣告支出。

**在以人物為基礎的管道中觸及對象，而不需要專用的資料上線解決方案或自訂工作流程來傳送對象。**

跨以人物為基礎的管道鎖定受眾的較為「傳統」的方式包括，您必須以您要廣告的平台接受的格式匯出客戶資料，然後使用平台的專用資料上線方法，將客戶資料帶入您的廣告商帳戶。 這是您需要針對每個要廣告的平台執行的所有手動工作。 此外，不同的平台可能有不同的資料格式要求，使得程式更加繁瑣。

![pbd-overview](assets/pbd-diagram.png)

透過[!DNL People-Based Destinations]，Audience Manager可協助您集中客戶資料、建立受眾區段，以及在多個以人物為基礎的管道中啟用這些資料。 您可以在Audience Manager使用者介面中執行這項操作，避免手動將資料上傳到每個平台的其他工作，讓您在此過程中節省寶貴時間。

**從純粹的離線設定檔建立並啟用對象區段。**

[!DNL People-Based Destinations]解決先前只能根據裝置活動啟用對象區段的問題。 透過[!DNL People-Based Destinations]，您可以從您自己的[!DNL CRM]中完全離線資料建立區段，並在以人物為基礎的平台中加以啟用。 此外，您可以將離線資料與Audience Manager中已擁有的裝置資料建立關聯。

**利用Audience Manager的資料控管和隱私權控制安全地處理客戶資料。**

[!DNL People-Based Destinations]要求您只能使用無法回覆的雜湊識別碼。 這樣就能減少手動將客戶資料上傳至每個目的地平台的相關風險。

觀看以下影片，瞭解使用[!UICONTROL People-Based Destinations]時的資料流程概觀。

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## 使用個案 {#use-cases}

為了協助您更清楚瞭解您應如何使用[!DNL People-Based Destinations]以及何時使用，以下是Audience Manager客戶可以使用此功能解決的兩個使用案例範例。

### 使用案例#1 {#use-case-1}

線上零售商想要透過社交平台觸及現有客戶，並根據他們先前的訂單向他們顯示個人化優惠。 透過[!DNL People-Based Destinations]，線上零售商可以從自己的[!DNL CRM]擷取雜湊電子郵件地址以進行Audience Manager、從自己的離線資料建立區段，並將這些區段傳送至他們想要廣告的社交平台，以最佳化其廣告支出。

### 使用案例#2 {#use-case-2}

航空公司有不同的客戶層級（銅、銀和金），並想要透過社交平台為每個層級提供個人化優惠。 該公司使用Audience Manager來分析網站上的客戶活動。 不過，並非所有客戶都使用航空公司的行動應用程式，其中部分客戶尚未登入公司網站。 公司對這些客戶擁有的唯一識別碼是會員ID和電子郵件地址。

若要在社群媒體和類似的以人物為基礎的頻道中鎖定他們，他們可以使用雜湊電子郵件地址做為識別碼，將其[!DNL CRM]的客戶資料上線到Audience Manager中。

接著，他們可以結合其離線資料與現有線上活動特徵，以建立可透過[!DNL People-Based Destinations]鎖定的新受眾區段。
