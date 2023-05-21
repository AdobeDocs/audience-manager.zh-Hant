---
description: 使用基於人的目的地將第一方受眾段發送到基於人的環境。 這些環境是屬於一個實體的封閉生態系統，該實體控制其中顯示的內容。 這些平台包括Facebook等社交平台，以及依靠客戶賬戶來個性化顯示內容的其他平台。
seo-description: Use people-based destinations to send first-party audience segments to people-based environments. These environments are closed ecosystems belonging to one entity that controls the content that is being displayed within it. They include social platforms such as Facebook, and other platforms that rely on customer accounts to personalize the displayed content.
seo-title: People-Based Destinations Overview and Use Cases
solution: Audience Manager
title: 概述與使用案例
feature: People-based Destinations
exl-id: 2edbda3b-e2a3-4a92-965b-206a21764cc8
source-git-commit: ab3361a0a54a7200d2f0c03a82ae6ef61a755be9
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 1%

---

# 概述與使用案例 {#overview-use-cases}

使用 [!DNL People-Based Destinations] 將第一方受眾片段發送到基於人的環境。 這些環境是屬於一個實體的封閉生態系統，該實體控制其中顯示的內容。 包括社交平台，如 [!DNL Facebook]以及其他依靠客戶帳戶來個性化顯示的內容的平台。

>[!IMPORTANT]
>本文包含旨在指導您完成此功能的設定和使用的產品文檔。 這裡沒有法律建議。 請咨詢您自己的法律顧問以獲得法律指導。

## 概述 {#overview}

[!DNL People-Based Destinations] 使您能夠在聯機和離線資料上應用分段以基於 [散列標識符](people-based-destinations-prerequisites.md#hashing-requirements)，如電子郵件地址。 然後，您可以將這些段發送到「有圍牆的花園」，例如 [!DNL Facebook]在社交平台上，你可以瞄準你的受眾。 [!DNL People-Based Destinations] 可幫助您：

* 在平台(如 [!DNL Facebook]，基於散列電子郵件地址；
* 補充現有設備和Cookie瞄準Audience Manager;
* 消除與第三方資料載入解決方案相關的成本；
* 消除與開發定制資料載入工作流相關的成本；
* 無Cookie環境中的目標受眾；
* 通過消除與客戶ID匹配的散列電子郵件地址來目標受眾。

您可以使用 [!DNL People-Based Destinations] 將可能未訪問您網站的高價值客戶細分為目標，或停止將目標鎖定在已離線轉換的客戶。 此外，您還可以 [!DNL Profile Merge Rules] 將您的離線第一方資料與您的線上第一方資料(包括來自其他Adobe Experience Cloud解決方案的客戶資料)相結合，以優化您的社交媒體廣告工作。

![pbd概述](assets/pbd-overview.png)

## 可用性 {#availability}

[!DNL People-Based Destinations] 是高級Audience Manager整合。 請聯繫您的Adobe代表以利用此高級功能。

## 為什麼應使用 [!UICONTROL People-Based Destinations] {#why-use}

**通過從Audience Manager中管理整個受眾細分，為客戶提供一致的跨渠道體驗。**

不通過Audience Manager在基於人的渠道中激活您的受眾群，將導致客戶訪問您的網站時看到的內容與他們看到的內容（例如，在他們的網站中）之間產生脫節的體驗 [!DNL Facebook] 源。 跨渠道實現一致的目標可以增加廣告收入，同時優化廣告支出。

**在基於人的渠道中接觸觀眾，而無需專用的資料寄宿解決方案或自定義工作流來發送觀眾。**

針對基於人的渠道的受眾的更「傳統」的方式是，您必須以您希望在平台上進行廣告的接受格式導出客戶資料，然後使用平台的專用資料登入方法將客戶資料帶到您的廣告客戶帳戶。 這是您需要為每個要播發的平台執行的所有手動工作。 另外，不同的平台可能有不同的資料格式要求，使處理過程更加繁瑣。

![pbd概述](assets/pbd-diagram.png)

通過 [!DNL People-Based Destinations],Audience Manager可幫助您集中客戶資料、構建受眾群，並跨多個基於人員的渠道進行激活。 您可以從Audience Manager用戶介面中完成這一切，避免手動將資料上載到每個平台的額外工作，從而節省流程中的寶貴時間。

**從純離線配置檔案建立和激活受眾段。**

[!DNL People-Based Destinations] 解決以前只能根據設備活動激活受眾段的問題。 與 [!DNL People-Based Destinations]，您可以從您自己的純離線資料建立段 [!DNL CRM]，並在以人為本的平台中激活它們。 此外，您還可以將離線資料與已Audience Manager的設備資料關聯起來。

**利用Audience Manager的資料治理和隱私控制來安全地處理客戶資料。**

[!DNL People-Based Destinations] 要求您只使用不可逆散列的標識符。 這降低了將客戶資料手動上傳到每個目標平台的風險。

在使用時觀看以下視頻以獲取資料流的概述 [!UICONTROL People-Based Destinations]。

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## 使用個案 {#use-cases}

幫助您更好地瞭解您應該如何使用和何時使用 [!DNL People-Based Destinations]，下面是兩個示例使用案例，Audience Manager客戶可以通過使用此功能來解決。

### 用例#1 {#use-case-1}

一家線上零售商希望通過社交平台接觸現有客戶，並根據他們之前的訂單向他們展示個性化的優惠。 與 [!DNL People-Based Destinations]，線上零售商可以從自己的郵箱中攝取哈希電子郵件地址 [!DNL CRM] Audience Manager，從自己的離線資料構建資料段，並將這些資料段發送到他們想要廣告的社交平台，從而優化他們的廣告支出。

### 用例#2 {#use-case-2}

航空公司有不同的客戶層（銅牌、銀牌和金牌），希望通過社交平台為每個層提供個性化服務。 公司使用Audience Manager分析網站上的客戶活動。 然而，並非所有客戶都使用該航空公司的移動應用，其中一些客戶還沒有登錄該公司的網站。 公司擁有的有關這些客戶的唯一標識符是成員資格ID和電子郵件地址。

為了通過社交媒體和類似的基於人的渠道將他們作為目標，他們可以從他們的客戶資料中 [!DNL CRM] Audience Manager中，使用散列電子郵件地址作為標識符。

接下來，他們可以將離線資料與其現有線上活動特徵相結合，構建新的受眾群，通過這些群體群可以瞄準 [!DNL People-Based Destinations]。
