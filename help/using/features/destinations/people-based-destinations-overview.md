---
description: '使用以人物為基礎的目的地，將第一方對象區段傳送至以人物為基礎的環境。 這些環境是屬於一個實體的封閉生態系統，可控制其中顯示的內容。 包括Facebook等社交平台，以及仰賴客戶帳戶來個人化顯示內容的其他平台。 '
seo-description: '使用以人物為基礎的目的地，將第一方對象區段傳送至以人物為基礎的環境。 這些環境是屬於一個實體的封閉生態系統，可控制其中顯示的內容。 包括Facebook等社交平台，以及仰賴客戶帳戶來個人化顯示內容的其他平台。  '
seo-title: 以人物為基礎的目的地概述和使用案例
solution: Audience Manager
title: 概述與使用案例
feature: 以人物為基礎的目的地
exl-id: 2edbda3b-e2a3-4a92-965b-206a21764cc8
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 1%

---

# 概述與使用案例 {#overview-use-cases}

使用[!DNL People-Based Destinations]將第一方對象區段傳送至以人物為基礎的環境。 這些環境是屬於一個實體的封閉生態系統，可控制其中顯示的內容。 其中包括[!DNL Facebook]等社交平台，以及依賴客戶帳戶來個人化顯示內容的其他平台。

>[!IMPORTANT]
>本文包含的產品檔案旨在引導您完成此功能的設定與使用。 這裡沒有任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

## 概述 {#overview}

[!DNL People-Based Destinations] 可讓您對線上和離線資料套用區段，以根據雜湊識別碼 [](people-based-destinations-prerequisites.md#hashing-requirements)（例如電子郵件地址或電話號碼）建立受眾區段。接著，您可以將這些區段傳送至「有圍牆的花園」，例如[!DNL Facebook]，以便在社交平台上鎖定您的對象。 [!DNL People-Based Destinations] 可協助您：

* 根據雜湊電子郵件地址，在平台（例如[!DNL Facebook]）中鎖定離線和線上對象；
* 補充Audience Manager的現有裝置和Cookie鎖定功能；
* 消除與第三方資料上線解決方案相關的成本；
* 消除開發自訂資料上線工作流程的相關成本；
* 在無Cookie環境中鎖定對象；
* 刪除與客戶ID相符的雜湊電子郵件地址重複，以鎖定對象。

您可以使用[!DNL People-Based Destinations]來劃分和鎖定可能未造訪過您網站的高價值客戶，或停止鎖定已離線轉換的客戶。 此外，您還可以利用[!DNL Profile Merge Rules]將離線第一方資料與您的線上第一方資料(包括來自其他Adobe Experience Cloud解決方案的客戶資料)結合，以最佳化您的社交媒體廣告成效。

![pbd-overview](assets/pbd-overview.png)

## 可用性 {#availability}

[!DNL People-Based Destinations] 是進階Audience Manager整合。請連絡您的Adobe代表，以利用此進階功能。

## 為何應使用[!UICONTROL People-Based Destinations] {#why-use}

**從Audience Manager內管理整個受眾細分，為客戶提供一致的跨管道體驗。**

不透過Audience Manager在以人物為基礎的管道中啟用您的對象區段，會導致客戶造訪網站時看到的內容與他們在[!DNL Facebook]摘要中看到的內容之間產生不連結的體驗。 跨管道擁有一致的鎖定目標可增加廣告收入，同時最佳化廣告支出。

**在以人物為基礎的管道中觸及受眾，而不需要專用的資料入門解決方案或自訂工作流程來傳送受眾。**

跨以人物為基礎的管道鎖定受眾的更「傳統」方式，包括您必須以平台接受的格式匯出客戶資料（您想要廣告的格式），然後使用平台的專用資料上線方法將客戶資料帶入廣告商帳戶。 這都是您需要針對每個要廣告的平台進行的手動操作。 此外，不同平台可能有不同的資料格式需求，使程式更加繁瑣。

![pbd-overview](assets/pbd-diagram.png)

透過[!DNL People-Based Destinations],Audience Manager可協助您集中客戶資料、建立受眾區段，並在多個以人物為基礎的管道中啟用這些區段。 您可以從Audience Manager使用者介面內完成這一切，避免手動上傳資料至每個平台的額外工作，為您節省流程中的寶貴時間。

**從純離線設定檔建立和啟用對象區段。**

[!DNL People-Based Destinations] 解決以前您只能根據裝置活動啟用受眾區段的問題。透過[!DNL People-Based Destinations]，您可以從自己的[!DNL CRM]中從純離線資料建立區段，並在以人物為基礎的平台中啟用這些區段。 此外，您可以將離線資料與已Audience Manager的裝置資料產生關聯。

**運用Audience Manager的資料控管和隱私權控制，以安全地處理客戶資料。**

[!DNL People-Based Destinations] 要求您僅使用不可逆轉的雜湊識別碼。這可降低手動將客戶資料上傳至每個目的地平台的相關風險。

觀看以下影片以了解使用[!UICONTROL People-Based Destinations]時的資料流程。

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## 使用個案 {#use-cases}

為協助您更清楚了解應如何及何時使用[!DNL People-Based Destinations]，以下是Audience Manager客戶可使用此功能解決的兩個範例使用案例。

### 使用案例#1 {#use-case-1}

線上零售商想要透過社交平台觸及現有客戶，並根據先前的訂單顯示個人化優惠方案。 透過[!DNL People-Based Destinations]，線上零售商可將雜湊電子郵件地址從自己的[!DNL CRM]擷取至Audience Manager、從自己的離線資料建立區段，並將這些區段傳送至他們要廣告的社交平台，以最佳化其廣告支出。

### 使用案例#2 {#use-case-2}

航空公司有不同的客戶層級（銅、銀和金），並想透過社交平台為每個層級提供個人化優惠方案。 公司使用Audience Manager來分析網站上的客戶活動。 不過，並非所有客戶都使用航空公司的行動應用程式，其中有些客戶尚未登入公司網站。 公司唯一與這些客戶有關的識別碼是會籍ID和電子郵件地址。

若要跨社交媒體和類似以人物為基礎的管道鎖定目標客戶，他們可以將[!DNL CRM]的客戶資料上線至Audience Manager，使用雜湊電子郵件地址做為識別碼。

接下來，他們可以結合其離線資料與現有的線上活動特徵，以建立新的受眾區段，並透過[!DNL People-Based Destinations]鎖定這些區段。
