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
source-git-commit: 0c9c333f4e8d6d416d497f336e3e447e2e251d47
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 1%

---


# 大量管理快速入門{#getting-started-with-bulk-management}

[!DNL Bulk Management Tools]可讓您透過單一作業一次建立和管理多個物件。 您可以使用[!DNL Bulk Management Tools]來處理[!UICONTROL data sources]、[!UICONTROL derived signals]、[!UICONTROL destinations]、[!UICONTROL folders]、[!UICONTROL models]、[!UICONTROL segments]和[!UICONTROL traits]。

>[!IMPORTANT]
>
>大量管理工具並非正式支援的Adobe產品。 客戶服務提供的疑難排解與支援將依個別情況處理。

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[在[!DNL Audience Manager]使用者介面中指派的RBAC群組許可權](../../features/administration/administration-overview.md)已在[!UICONTROL Bulk Management Tools]中接受。

## 概述 {#overview}

此功能使用含有巨集的[!DNL Microsoft Excel]試算表，向[!DNL Audience Manager] API發出經驗證的安全呼叫。 API提供可讓您大量進行變更的方法與服務。 您不需要知道如何編寫程式碼或使用我們的API即可使用。 工作表包含執行特定大量變更功能的欄位標題與頁標。 若要進行大量變更，您只需將預先定義的標題新增至特定工作表、提供要大量變更的資訊，然後按一下動作按鈕。 工作表和API會為您完成其餘的工作。

## 下載 {#download}

在&#x200B;**[這裡](assets/BAAAM_V2_20210609.xlsm)**&#x200B;下載最新的工作表（最後更新於2021年6月）。

## 先決條件 {#prereqs}

若要使用[!DNL Bulk Management Tools]，您需要下列專案：

* 您的[!DNL Experience Cloud]登入。 身為客戶，您應該已經擁有這些認證。
* [!DNL Bulk Management Tools]工作表。 [下載工作表](assets/BAAAM_V2_20210609.xlsm)以取得最新版本。
* 在64位元[!DNL Microsoft Windows]上執行的[!DNL Microsoft Excel]。 建議您使用最新版本的[!DNL Microsoft Excel]。 [!DNL macOS]不支援大量管理工具。
* 開啟工作表時，您必須&#x200B;**啟用巨集**&#x200B;才能讓[!DNL Bulk Management Tools]運作。

## 驗證需求和選項 {#auth-reqs}

大量變更需要驗證。 您必須先登入，才能執行任何動作。 由於工作表會進行API呼叫，因此您需要將其設定為驗證您的使用者帳戶。

**API驗證需求**

於2019年10月發行的[!DNL Bulk Management Tools]第二版簡化了驗證程式。 此版本中的驗證步驟概述如下：

1. 開啟試算表並導覽至&#x200B;**[!UICONTROL Config]**&#x200B;工作表。
2. 請遵循工作表中概述的步驟。
   ![](assets/baaam-authentication.png)
3. 完成步驟後，您有權進行大量變更。

進行大量變更時，您仍須確認您有權進行變更，但API驗證會自動完成。

**網域驗證選項**

網域驗證可讓您選擇測試大量請求，或直接將其套用至您的生產帳戶。 對測試版環境進行大量變更將不會影響您的生產帳戶。 生產變更會立即生效。 大量管理工作表可讓您在下列環境中工作：

* Beta
* 生產

## 動作與作業 {#actions-ops}

[!UICONTROL Bulk Management Tools]工作表包含驗證按鈕、動作標籤、動作按鈕和&#x200B;**[!UICONTROL Headers]**&#x200B;標籤。 **[!UICONTROL Headers]**&#x200B;索引標籤包含動作索引標籤使用的預先格式化的欄標題。 動作標籤包含執行您選取之大量作業的巨集。 若要執行大量作業，請將一組標頭複製到適當的動作索引標籤中，輸入標頭資料，然後按一下動作按鈕。

在[驗證](#auth-reqs)之後，按一下動作按鈕即可開始。

![](assets/baaam-worksheet.png)

下表列出您可以執行的作業，以及可以使用[!UICONTROL Bulk Management Tools]工作表處理的專案。

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
   <td colname="col2"> <p>您可以大量變更的物件位於<b><span class="uicontrol"> Headers</span></b>標籤下，並包含： </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings">資料來源</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md">衍生訊號</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md">個目的地</a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md">個模型</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage">特徵資料夾</a>和區段資料夾 </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md">區段</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md">特徵</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**大量作業範例**

舉例來說，我們來看看如何同時建立多個特徵。 若要以大量作業建立多個特徵，您可以：

1. 按一下「**[!UICONTROL Headers]**」標籤，並複製[!UICONTROL Create a Trait]選項下的所有標籤。
2. 按一下「**[!UICONTROL Create]**」標籤，貼上從列1欄A開始的標籤。
3. 提供每個欄標題的相關資訊，然後按一下&#x200B;**[!UICONTROL Create Traits]**。 這個動作會提示您確認驗證。 在您確認驗證後，您的大量工作就會執行。 檢查工作表左下角的工作狀態通知。


>[!NOTE]
>
>處理大型請求時，工作表可能會變得無回應，並且似乎處於非使用中狀態。 在這些情況下，不要管它。 當大量請求完成時，工作表將變得有回應。 如果工作表長時間沒有回應，請參閱[疑難排解區段](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
