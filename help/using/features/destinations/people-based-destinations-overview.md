---
description: '使用以人為本的目的地，將第一方受眾細分傳送至以人為本的環境。 這些環境是屬於一個實體的封閉生態系統，控制其中顯示的內容。 這些平台包括Facebook等社交平台，以及依賴客戶帳戶個人化顯示內容的其他平台。 '
seo-description: '使用以人為本的目的地，將第一方受眾細分傳送至以人為本的環境。 這些環境是屬於一個實體的封閉生態系統，控制其中顯示的內容。 這些平台包括Facebook等社交平台，以及依賴客戶帳戶個人化顯示內容的其他平台。  '
seo-title: 基於人員的目標概觀和使用案例
solution: Audience Manager
title: 概觀與使用案例
translation-type: tm+mt
source-git-commit: 0eb6a6f67d87377a044b18118fac0185219b0347

---


# 概觀與使用案例 {#overview-use-cases}

使用 [!DNL People-Based Destinations] 將第一方受眾細分傳送至以人為本的環境。 這些環境是屬於一個實體的封閉生態系統，控制其中顯示的內容。 這些平台包括社交平台， [!DNL Facebook]以及依賴客戶帳戶個人化顯示內容的其他平台。

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

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

更「傳統」的跨人類通道鎖定受眾方式包括，您必須以平台所接受的格式匯出客戶資料，然後使用平台專用的資料登入方法將客戶資料匯入廣告商帳戶。 這些都是您需要針對每個要廣告的平台進行的手動工作。 此外，不同平台可能有不同的資料格式需求，使程式變得更加繁複。

![pbd-overview](assets/pbd-diagram.png)

透過 [!DNL People-Based Destinations]Audience manager，您可以幫助您集中管理客戶資料、建立受眾細分，並跨多個以人為本的通道加以啟用。 您可以從Audience Manager UI中完成這一切，避免手動上傳資料至每個平台的額外工作，為您節省流程中的寶貴時間。

**從純離線個人檔案建立並啟用受眾細分。**

[!DNL People-Based Destinations] 解決先前您只能根據裝置活動啟用受眾細分的問題。 有了 [!DNL People-Based Destinations]，您就可以從自己的純線下資料建立區段 [!DNL CRM]，並在以人為本的平台中加以啟動。 此外，您可以將離線資料與Audience manager中已有的裝置資料建立關聯。

**運用Audience manager的資料管理和隱私權控制，以安全地處理客戶資料。**

[!DNL People-Based Destinations] 要求您僅使用不可逆轉的雜湊識別碼。 這可降低手動將客戶資料上傳至每個目標平台的相關風險。

觀看以下影片，瞭解使用時的資料流程 [!UICONTROL People-Based Destinations]。

[!VIDEO](https://video.tv.adobe.com/v/28968/?captions=chi_hant)

## 使用個案 {#use-cases}

為協助您更清楚瞭解應如何及何時使用 [!DNL People-Based Destinations]，以下是Audience manager客戶可使用此功能解決的兩個範例使用案例。

### Use Case #1 {#use-case-1}

線上零售商想透過社交平台接觸現有客戶，並根據先前的訂單向他們展示個人化優惠。 有了 [!DNL People-Based Destinations][!DNL CRM] ，線上零售商可以將雜湊的電子郵件地址從自己的Audience Manager中收錄、從自己的離線資料建立區段，並將這些區段傳送至他們想要廣告的社交平台，以最佳化其廣告支出。

### Use Case #2 {#use-case-2}

航空公司有不同的客戶層級（銅、銀和金），並希望透過社交平台為每個層級提供個人化優惠。 該公司使用Audience manager分析網站上的客戶活動。 不過，並非所有客戶都使用該航空公司的行動應用程式，其中有些客戶尚未登入該公司網站。 公司對於這些客戶的唯一識別碼是會籍ID和電子郵件地址。

若要跨社交媒體和類似以人為本的通道鎖定客戶，他們可以將客戶資料從雜湊的電子郵件地址當成識別碼，從 [!DNL CRM] Audience Manager中將其帶入客戶資料。

接下來，他們可以結合線下資料和現有的線上活動特徵，以建立新的受眾細分，並透過這些細分進行鎖定 [!DNL People-Based Destinations]。
