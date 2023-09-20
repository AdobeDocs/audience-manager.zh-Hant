---
description: 「大量管理工具」可讓您透過單一操作一次建立和管理多個物件。 您可以使用大量管理工具來處理資料來源、衍生訊號、目的地、資料夾、區段和特徵。
keywords: baaam；BAAAM；下載baaam
seo-description: The Bulk Management Tools let you create and manage multiple objects at once with single operation. You can use Bulk Management Tools to work with data sources, derived signals, destinations, folders, segments, and traits.
seo-title: Getting Started With Bulk Management
solution: Audience Manager
title: 大量管理快速入門
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: BAAAM
exl-id: 5603146e-7172-4181-90ad-4606129176dd
source-git-commit: 6b4796db4fc336180d72d4971b4f267fcc42d398
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 3%

---


# 大量管理快速入門{#getting-started-with-bulk-management}

此 [!DNL Bulk Management Tools] 可讓您透過單一操作一次建立和管理多個物件。 您可以使用 [!DNL Bulk Management Tools] 使用 [!UICONTROL data sources]， [!UICONTROL derived signals]， [!UICONTROL destinations]， [!UICONTROL folders]， [!UICONTROL models]， [!UICONTROL segments]、和 [!UICONTROL traits].

>[!IMPORTANT]
>
>大量管理工具並非正式支援的Adobe產品。 客戶服務提供的疑難排解與支援將依個別情況處理。

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[RBAC群組許可權](../../features/administration/administration-overview.md) 指派於 [!DNL Audience Manager] 使用者介面遵循於 [!UICONTROL Bulk Management Tools].

## 概述 {#overview}

此功能使用 [!DNL Microsoft Excel] 以巨集建立試算表，向發出經過驗證的安全呼叫 [!DNL Audience Manager] API。 API提供可讓您大量進行變更的方法與服務。 您不需要知道如何編寫程式碼或使用我們的API即可使用。 工作表包含執行特定大量變更功能的欄位標題與頁標。 若要進行大量變更，您只需將預先定義的標題新增至特定工作表、提供要大量變更的資訊，然後按一下動作按鈕。 工作表和API會為您完成其餘的工作。

## 下載 {#download}

下載最新的工作表 **[此處](assets/BAAAM_V2_20210609.xlsm)** （上次更新日期：2021年6月）。

## 必要條件 {#prereqs}

若要使用 [!DNL Bulk Management Tools]，您需要下列專案：

* 您的 [!DNL Experience Cloud] 登入。 身為客戶，您應該已經擁有這些認證。
* 此 [!DNL Bulk Management Tools] 工作表。 [下載工作表](assets/BAAAM_V2_20200502.xlsm) 以取得最新版本。
* [!DNL Microsoft Excel] 執行於 [!DNL macOS] 或64位元 [!DNL Microsoft Windows]. 建議您使用最新版本的 [!DNL Microsoft Excel].
* 開啟工作表時，您必須 **啟用巨集** 針對 [!DNL Bulk Management Tools] 才能運作。

## 驗證需求和選項 {#auth-reqs}

大量變更需要驗證。 您必須先登入，才能執行任何動作。 由於工作表會進行API呼叫，因此您需要將其設定為驗證您的使用者帳戶。

**API驗證需求**

第二版的 [!DNL Bulk Management Tools]於2019年10月發行，可簡化驗證程式。 此版本中的驗證步驟概述如下：

1. 開啟試算表，並導覽至 **[!UICONTROL Config]** 工作表。
2. 請遵循工作表中概述的步驟。
   ![](assets/baaam-authentication.png)
3. 完成步驟後，您有權進行大量變更。

進行大量變更時，您仍須確認您有權進行變更，但API驗證會自動完成。

**網域驗證選項**

網域驗證可讓您選擇測試大量請求，或直接將其套用至您的生產帳戶。 對測試版環境進行大量變更將不會影響您的生產帳戶。 生產變更會立即生效。 大量管理工作表可讓您在下列環境中工作：

* Beta
* 生產

## 動作與作業 {#actions-ops}

此 [!UICONTROL Bulk Management Tools] 工作表包含認證按鈕、作業頁標、作業按鈕及 **[!UICONTROL Headers]** 標籤。 此 **[!UICONTROL Headers]** 索引標籤包含動作索引標籤使用的預先格式化欄標題。 動作標籤包含執行您選取之大量作業的巨集。 若要執行大量作業，請將一組標頭複製到適當的動作索引標籤中，輸入標頭資料，然後按一下動作按鈕。

晚於 [驗證](#auth-reqs)，按一下動作按鈕開始。

![](assets/baaam-worksheet.png)

下表列出您可以執行的操作以及可以使用 [!UICONTROL Bulk Management Tools] 工作表。

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 動作 </th> 
   <th colname="col2" class="entry"> 物件 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>大量動作會出現在工作表底部的頁標中，並包含： </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">請求 </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">更新 </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">建立 </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">預估 </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">刪除 </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>您可以大量變更的物件位於 <b><span class="uicontrol"> 標頭</span></b> 標籤並包含： </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 資料來源</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> 衍生訊號</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> 目的地</a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> 模型</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> 特徵資料夾</a> 和區段資料夾 </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> 區段</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> 特徵</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**大量作業範例**

舉例來說，我們來看看如何同時建立多個特徵。 若要以大量作業建立多個特徵，您可以：

1. 按一下 **[!UICONTROL Headers]** 標籤並複製 [!UICONTROL Create a Trait] 選項。
2. 按一下 **[!UICONTROL Create]** 並貼上從列1欄A開始的標籤。
3. 提供與每個欄標題相關的資訊，然後按一下 **[!UICONTROL Create Traits]**. 這個動作會提示您確認驗證。 在您確認驗證後，您的大量工作就會執行。 檢查工作表左下角的工作狀態通知。


>[!NOTE]
>
>處理大型請求時，工作表可能會變得無回應，並且似乎處於非使用中狀態。 在這些情況下，不要管它。 當大量請求完成時，工作表將變得有回應。 如果工作表長時間沒有回應，請參閱 [疑難排解章節](../../reference/bulk-management-tools/bulk-troubleshooting.md).
