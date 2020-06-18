---
description: 進一步參閱資料的定義與連結。
seo-description: 進一步參閱資料的定義與連結。
seo-title: 字彙表
solution: Audience Manager
title: 字彙表
uuid: 01fc26f5-db9d-4e90-b4c1-27c6a510accc
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 100%

---


# 字彙表{#glossary}

進一步參閱資料的定義與連結。

## A-B {#a-b}

**演算法建模**

將 [!UICONTROL Algorithmic Modeling] 作為工具，將觸及延伸到您所識別使用者的核心以外。此功能可協助您透過自動化資料分析，挖掘出新的不重複受眾。在 **[!UICONTROL Audience Data > Models]** 中管理您的 [!UICONTROL Algorithmic Models]。

請參閱[瞭解演算法模型](../features/algorithmic-models/algo-models-overview.md)。

<br> 

**BAAAM**

[!UICONTROL Bulk Management Tools]。[!DNL Audience Manager] 中的 [!UICONTROL Bulk Management Tools] 是一組以 Microsoft Excel 為基礎的工具，可讓您透過單一操作一次建立、修改或刪除多個受眾。您可以使用資料來源、衍生訊號、目的地、資料夾、區段和特徵。此功能使用 Microsoft Excel 試算表及巨集，向 [!DNL Audience Manager] API 發出經驗證的安全呼叫。

請參閱[大量管理工具](../reference/bulk-management-tools/bulk-management-intro.md)。

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]。[!UICONTROL CDF] 檔案代表大量下載 [!DNL Audience Manager] 所收集的資料，可讓您不受使用者介面的限制使用 [!DNL Audience Manager] 資料。[!UICONTROL CDF] 檔案包含的資料與 [!DNL Audience Manager] 事件呼叫 (`/event`) 傳送至我們伺服器的資料相同。這包括使用者 ID、特徵 ID、區段 ID 等資料，以及事件呼叫所擷取的所有其他參數。

請參閱[客戶資料摘要](../features/cdf-files.md)。

<br> 

**CRM ID**

CRM ID 是客戶用於識別其 CRM 系統中使用者的 ID。我們在 Audience Manager 中使用的是 DPUUID 一詞，而非 CRM ID。

請參閱 [Audience Manager 內的 ID 索引](../reference/ids-in-aam.md)中的 DPUUID。

<br> 

**客戶可定址的受眾**

在[可定址的受眾](/help/using/features/addressable-audiences.md)中，此量度代表具備下列條件的裝置：
* 已在回顧期間實現了規則型或已上線特徵
   **和**
* 具有與所選目的地同步的 ID (不論同步的時間為何)。

<br> 

**客戶屬性**

請參閱 [!DNL Experience Cloud Core Services] 產品文件中的[客戶屬性](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/customer-attributes/attributes.html)。

<br> 

**客戶符合率**

客戶可定址的受眾 ÷ 客戶總受眾，以 % 表示。請參閱[可定址的受眾](/help/using/features/addressable-audiences.md)。

<br> 

**客戶總受眾**

在[可定址的受眾](/help/using/features/addressable-audiences.md)中，此量度代表在回顧期間，已在您的屬性上實現規則型特徵或離線檔案中已上線特徵的裝置計數。

<br> 

**demdex.net**

demdex.net 是由 [!DNL Adobe] 控制的舊網域。它反映出 [!DNL Audience Manager] 收購前的原來名稱 ([!DNL Demdex])。[!DNL Adobe] 於 2011 年收購 [!DNL Demdex]，並將該公司重新命名為 [!DNL Audience Manager]。所有對 `demdex.net` 網域發出的 HTTP 呼叫都是傳送至 [!DNL Adobe] 的呼叫。

請參閱[瞭解向 Demdex 網域進行的呼叫](../reference/demdex-calls.md)。

<br> 

**DAID**

[!UICONTROL Device Advertising IDs] 是不重複裝置識別碼，用來識別行動裝置。這些 ID 是由裝置製造商指派，而非由 Adobe 指派。[!DNL Audience Manager] 支援 iOS 和 Android 裝置 ID。

請參閱 [Audience Manager 內的 ID 索引](../reference/ids-in-aam.md)。

<br> 

**目的地**

在 [!DNL Audience Manager] 中，目的地是您想要與其共用資料的任何其他系統 (廣告伺服器、DSP、廣告網路等)。我們 UI 中的 [!UICONTROL Destination Builder] 提供工具，可讓您建立和管理這些資料傳送程序。[!DNL Audience Manager] 目的地功能位於 **[!UICONTROL Audience Data > Destinations]** 中。

<br> 

**DIL**

[!UICONTROL Data Integration Library] 是 API 程式庫，[!DNL Audience Manager] 用於收集使用者的互動資料。請參閱 [Data Integration Library (DIL) API](../dil/dil-overview.md)。

<br> 

**dpm**

[!UICONTROL Data Provider Match]。它會告訴內部 [!DNL Adobe] 系統，來自 [!DNL Audience Manager] 或 ID 服務的呼叫正傳入客戶資料以進行同步或請求 ID。請參閱[瞭解向 Demdex 網域進行的呼叫](../reference/demdex-calls.md)。

## E-F {#e-f}

**Experience Cloud ID (ECID)**

先前名為 [!DNL Marketing Cloud] ID (MID 或 MCID)。[!DNL Experience Cloud] ID 是 ID 服務的中心。它是網站訪客的不重複永久識別碼。請參閱 Cookie 和 [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/intro/cookies.html)。

<br> 

**資料夾特徵**

自動分組資料夾分類法中的特徵。階層中的每個資料夾都會自動建立可用來定義區段的特徵。

請參閱[資料夾特徵：關於](../features/traits/about-folder-traits.md)。

<br> 

**頻率限定**

廣告商想要向使用者顯示特定創意內容次數限制。您可以在 [!UICONTROL Segment Builder] 中設定各種頻率限定運算式。

請參閱[造訪間隔和頻率](../features/segments/recency-and-frequency.md)。

## G-H {#g-h}

**GAID**

Google Advertising ID，這是 Google 指派給執行 Android 作業系統之硬體裝置的不重複裝置 ID。請參閱 [Audience Manager 內的 ID 索引](../reference/ids-in-aam.md)。

<br> 

**GUID**

全域唯一識別碼的縮寫。[!DNL Audience Manager] 中不使用 GUID 一詞。我們將 GUID 稱為 [!DNL Audience Manager] UUID。
請參閱 [Audience Manager 內的 ID 索引](../reference/ids-in-aam.md)。

## I-J {#i-j}

**IDFA**

廣告商的識別碼，是 Apple 指派給其產品的不重複裝置 ID。請參閱 [Audience Manager 內的 ID 索引](../reference/ids-in-aam.md)。

<br> 

**傳入**

從其他來源將受眾資料傳送至 [!DNL Audience Manager] 的程序。請參閱[傳送受眾資料](/help/using/integration/sending-audience-data/send-audience-data.md)。

<br> 

**整合程式碼**

使用 [!DNL Audience Manager] UI 或 API 時，您可以在建立特徵、區段或資料來源時新增整合程式碼。在以下情況中，整合程式碼有不同的用途：

* [!UICONTROL Traits]：整合程式碼是您內部業務流程所使用的 ID、SKU 或其他值的欄位。選填。
* [!UICONTROL Segments]：整合程式碼是使用者定義的 ID 或其他公司專屬資訊的欄位。選填。
* [!UICONTROL Data Sources]：當您想要建立跨裝置資料來源、使用 Adobe Experience Platform Identity Service 或使用 [!UICONTROL Profile Merge Rules] 時，會需要整合程式碼。請參閱[建立資料來源](../features/manage-datasources.md#create-data-source)，瞭解更多資訊。

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

請參閱[演算法建模](../reference/aam-glossary.md#a-b)。

## M-N {#m-n}

**MCID**、**MID**

請參閱 [Experience Cloud ID](../reference/aam-glossary.md#e-f)。

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]。[!UICONTROL PCS] 是一個大型資料庫，在 Apache Cassandra 上運作。它會儲存從伺服器對伺服器的傳輸和 [!DNL DCS] 中接收到的作用中使用者資料。[!UICONTROL PCS] 資料包含裝置 ID、已驗證的設定檔 ID 及其相關特徵。

請參閱[資料收集元件](../reference/system-components/components-data-collection.md)。

<br> 

**設定檔連結**

請參閱[定義的設定檔合併規則選項](../features/profile-merge-rules/merge-rule-definitions.md)。

<br> 

**設定檔合併規則**

[!UICONTROL Profile Merge Rules] 可讓您控制 [!DNL Audience Manager] 用於細分的資料類型。

請參閱[定義的設定檔合併規則選項](../features/profile-merge-rules/merge-rule-definitions.md)。

## Q-R {#q-r}

**實現**

訪客在您網站上符合特徵資格的動作。您可以使用[訪客設定檔檢視器](../features/visitor-profile-viewer.md)工具，取得特定使用者特徵實現的相關資訊。

## S-T {#s-t}

**區段**

區段 (或受眾) 是具有共同屬性的一組使用者。

請參閱[區段：用途、構成和規則](../features/segments/segments-purpose.md)。

<br> 

**區段可定址的受眾**

在[可定址的受眾](/help/using/features/addressable-audiences.md)中，此量度代表在報表回顧期間屬於區段，且在您的網站上具有同步作用中 ID 的使用者人數。區段可以透過在 [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md) 中取得的特徵，包含您自己的第一方資料、第二方資料和第三方資料。

<br> 

**區段總母體**

在[可定址的受眾](/help/using/features/addressable-audiences.md)中，此量度代表報表回顧期間屬於您區段的所有裝置計數。

<br> 

**區段符合率**

區段可定址的受眾 ÷ 區段總母體，以 % 表示。請參閱[可定址的受眾](/help/using/features/addressable-audiences.md)。

<br> 

**訊號**

訊號是 [!DNL Audience Manager] 中最小的資料單位，以索引鍵值配對表示。

請參閱[訊號、特徵和區段](../reference/signal-trait-segment.md)。

<br> 

**特徵**

特徵是一或多個訊號的組合。請參閱[訊號、特徵和區段](../reference/signal-trait-segment.md)。

<br> 

**特徵母體**

請參閱[區段產生器的特徵和區段母體資料](../features/segments/segment-builder-data.md)。

**TTL (存留時間)**

TTL 會定義合格訪客在某個特徵中停留的天數。TTL 是針對特徵設定而非區段。如果在 TTL 間隔結束前沒有看到訪客符合特徵資格，訪客便會從區段中流失。如需深入瞭解，請參閱[區段和特徵存留時間說明](/help/using/features/traits/segment-ttl-explained.md)。

<br> 

## U-V {#u-v}

**UUID**

[!DNL Audience Manager] 不重複使用者 ID。請參閱 [Audience Manager 內的 ID 索引](../reference/ids-in-aam.md)。

<br> 

**訪客 ID**

[!DNL Experience Cloud] ID 服務 (前身為「ID 服務」) 提供永久性的通用 ID，可識別 [!DNL Experience Cloud] 中所有解決方案的訪客。

請參閱 [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.translate.html) 文件。

## W-X-Y-Z {#w-z}

