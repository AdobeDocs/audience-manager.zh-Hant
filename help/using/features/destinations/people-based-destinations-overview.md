---
description: '使用以人為本的目的地，將第一方受眾細分傳送至以人為本的環境。 這些環境是屬於一個實體的封閉生態系統，控制其中顯示的內容。 這些平台包括Facebook等社交平台，以及依賴客戶帳戶個人化顯示內容的其他平台。 '
seo-description: '使用以人為本的目的地，將第一方受眾細分傳送至以人為本的環境。 這些環境是屬於一個實體的封閉生態系統，控制其中顯示的內容。 這些平台包括Facebook等社交平台，以及依賴客戶帳戶個人化顯示內容的其他平台。  '
seo-title: 基於人員的目標概觀和使用案例
solution: Audience Manager
title: 概述與使用案例
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 1%

---


# 概述與使用案例 {#overview-use-cases}

使用[!DNL People-Based Destinations]將第一方受眾細分傳送至以人員為基礎的環境。 這些環境是屬於一個實體的封閉生態系統，控制其中顯示的內容。 這些平台包括[!DNL Facebook]等社交平台，以及依賴客戶帳戶個人化顯示內容的其他平台。

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

## 概述 {#overview}

[!DNL People-Based Destinations] 可讓您針對線上和離線資料套用區段，以根據雜湊識別碼(例如 [電子郵件地址](people-based-destinations-prerequisites.md#hashing-requirements)或電話號碼)建立觀眾區段。然後，您可以將這些區段傳送至「圍牆花園」，例如[!DNL Facebook]，以便鎖定社交平台上的受眾。 [!DNL People-Based Destinations] 可協助您：

* 根據雜湊的電子郵件地址，鎖定[!DNL Facebook]等平台的離線和線上觀眾；
* 補充Audience Manager現有的裝置和Cookie定位功能；
* 免除與第三方資料上線解決方案相關的成本；
* 免除開發自訂資料上線工作流程的相關成本；
* 在無Cookie環境中鎖定受眾；
* 借由消除與客戶ID相符的雜湊電子郵件地址，以鎖定受眾。

您可以使用[!DNL People-Based Destinations]來區隔並鎖定未瀏覽您網站的高價值客戶，或停止鎖定已離線轉換的客戶。 此外，您還可以運用[!DNL Profile Merge Rules]來結合您的離線第一方資料和您的線上第一方資料，包括來自其他Adobe Experience Cloud解決方案的客戶資料，以最佳化您的社交媒體廣告成果。

![pbd-overview](assets/pbd-overview.png)

## 可用性 {#availability}

[!DNL People-Based Destinations] 是Audience Manager的進階整合。請連絡您的Adobe代表，以利用這項優質功能。

## 為何應使用[!UICONTROL People-Based Destinations] {#why-use}

**從Audience Manager管理整個受眾細分，為客戶提供一致的跨通道體驗。**

不透過Audience Manager在以人為本的通道中啟動受眾細分，會導致客戶在瀏覽您的網站時看到的內容與他們在[!DNL Facebook]摘要中看到的內容之間產生脫節的體驗。 跨通道擁有一致的定位，可以增加廣告收入，同時最佳化廣告支出。

**在以人為本的通道中觸及受眾，而不需使用專屬的資料入門解決方案或自訂工作流程來傳送受眾。**

更「傳統」的跨人類通道鎖定受眾方式包括，您必須以平台所接受的格式匯出客戶資料，然後使用平台專用的資料登入方法將客戶資料匯入廣告商帳戶。 這些都是您需要針對每個要廣告的平台進行的手動工作。 此外，不同平台可能有不同的資料格式需求，使程式變得更加繁複。

![pbd-overview](assets/pbd-diagram.png)

透過[!DNL People-Based Destinations],Audience Manager可協助您集中化客戶資料、建立受眾細分，並跨多個以人為本的通道加以啟用。 您可以從Audience Manager使用者介面中完成這一切，避免手動上傳資料至每個平台的額外工作，為您節省流程中的寶貴時間。

**從純離線個人檔案建立並啟用受眾細分。**

[!DNL People-Based Destinations] 解決先前您只能根據裝置活動啟用受眾細分的問題。使用[!DNL People-Based Destinations]，您可以從您自己的[!DNL CRM]中建立純離線資料的區段，並在以人員為主的平台中加以啟動。 此外，您可以將離線資料與Audience Manager中已有的裝置資料建立關聯。

**運用Audience Manager的資料管理和隱私權控制，以安全地處理客戶資料。**

[!DNL People-Based Destinations] 要求您僅使用不可逆轉的雜湊識別碼。這可降低手動將客戶資料上傳至每個目標平台的相關風險。

觀看以下視訊，瞭解使用[!UICONTROL People-Based Destinations]時的資料流程。

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## 使用個案 {#use-cases}

為協助您更清楚瞭解應如何及何時使用[!DNL People-Based Destinations]，以下是Audience Manager客戶可使用此功能解決的兩個範例使用案例。

### 使用案例#1 {#use-case-1}

線上零售商想透過社交平台接觸現有客戶，並根據先前的訂單向他們展示個人化優惠。 透過[!DNL People-Based Destinations]，線上零售商可將其[!DNL CRM]中的雜湊電子郵件地址收錄至Audience Manager，從其自身的離線資料建立區段，並將這些區段傳送至他們想要廣告的社交平台，最佳化其廣告支出。

### 使用案例#2 {#use-case-2}

航空公司有不同的客戶層級（銅、銀和金），並希望透過社交平台為每個層級提供個人化優惠。 該公司使用Audience Manager分析網站上的客戶活動。 不過，並非所有客戶都使用該航空公司的行動應用程式，其中有些客戶尚未登入該公司網站。 公司對於這些客戶的唯一識別碼是會籍ID和電子郵件地址。

若要跨社交媒體和類似的以人為本的通道鎖定客戶，他們可以將[!DNL CRM]的客戶資料載入Audience Manager，使用雜湊的電子郵件地址做為識別碼。

接著，他們可結合其離線資料和現有的線上活動特徵，以建立新的受眾細分，並透過[!DNL People-Based Destinations]加以鎖定。
